# TDD

## Karma 導論
[Karma] (http://karma-runner.github.io/) 是一個測試執行器 (test runner)，它能夠讓人輕鬆地以驚人的速度來執行測試，其中利用 [node.js](http://www.nodejs.org/) 和 [SocketIO](http://www.socket.io/) 在多個瀏覽器輕易且迅速的執行測試。

**測試執行器 (*Test Runner*) 與測試框架 (*Testing Framework*)**
```
當使用 JS (與 AngularJS ) 時，對於每個任務，分別有不同的工具或函式庫來處理。Karma 是一田人口十測試執行，全權負責找尋程式碼庫裡的所有單元測試、開啟瀏覽器、執行測試、並獲取結果。它不在乎測試用的程式是使用哪種語言或框架來撰寫，它只是負責執行測試。

Jasmin 則是測試框架。Jasmine 定義與測試有關的語法、APIs 以及撰寫斷言的方法。當可以不使用 Jasmine，而用類似 mocha 或其它一些框架撰寫 AngularJS 的測試。
```

### Karma 外掛程式 (plugins) ###
#### 瀏覽器啟動器 (*launchers*) ####
#### 測試框架 ####
#### 回報器 (*reporters*) ####
#### 整合 (*Integrations*) ####

## Jasmine: 測試的規格形式 ##
Jasmine 框架使用行為驅動 (behavior-driven) 形式來撰寫測試，我們描述行為以及設定預期內容 (expectations) 而非撰寫一堆函式與斷言 (asserts)。

### Jasmine 語法 ###
```
// Jasmine test suite
describe( 'My function', function() {
  var t;
  beforeEach( function() {
    t = true;
  });
  
  afterEach( function() {
    t = null;
  });
  
  it( 'should perform action 1', function() {
    expect(t).toBeTruthy();
  });
  it( 'should perform action 2', function() {
    expect(t).toEaual( expectedValue );
  });
});
```
_describe_
  測試程式的最開頭建立一組測試套件。把測試套件當作是用於多個單元測試的一個容器，針對 controller, service 等等寫一個 describe 巢狀包含多個 describe。
_beforeEach_
  beforeEach 類似 xUnit 測試範式的設置函式 (setup function)。也就是說，傳遞給 beforeEach 的函式所含內容會在每個個別的 it 區塊之前被執行。
_afterEach_
  afterEach 區塊在各自的 it 區塊運作完成之後執行，如果使用模擬的 (mocking) 函式庫，這個位置是檢查模擬 (mocks) 上面的任何預期內容是否滿足的最佳之處。
_it_
  這些是單元測試。每個 it 區塊應該是各自獨立而與其他 it 區塊無關。在 it 裡面，會基本的設置狀態、執行函式、檢查傳回值(return value) 以及確保所有的預期內容都得到滿足。
_expect_
  這些與 Jasmine 的 assert 陳述句對等。每個 expect 帶入一個值，接著可以使用其中一個內建（或自訂的）matches 來檢查這個被帶入的值。
  
### 有用的 matchers ###
##### toEqual #####
##### toBe #####
##### toBeTruthy #####
##### toBeFalsy #####
##### toBeDefined #####
##### toBeUndefined #####
##### toBeNull #####
##### toContain #####
##### toMatch #####
