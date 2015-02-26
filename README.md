# ProgrammingPocketList

放一些我找到跟程式設計有關的口袋名單，可能是好用的SDK或是其他的．主要用中文寫，我想英文有太多可以參考了． 

內容列表:

- [Golang](#Golang)
    - [Challenge / Testing / Tutorial](#Challenge / Testing / Tutorial)
    - [Error Handle](#Error Handle)
    - [Toolkit](#Toolkit)
    - [Other Go List](#OtherGoList)
    
    
# Golang


##Challenge / Testing / Tutorial
- [Operation Go](http://gocode.io/)
    - 透過扮演兩個探員的故事，裡面穿插很多Go programing的測驗．

##Error Handle

- [Golang] [GoPanic](https://github.com/joedborg/gopanic) Panic 是Go裡面一個發生錯誤會呼叫的函式，其實只是做memory dump而以．但是為了避免Panic 發生的時候，一些資料被竊取． 
    - [Cold Boot Attack](http://en.wikipedia.org/wiki/Cold_boot_attack):原本指的是加密的key寫在記憶體，卻被冷卻後移除電腦而直接讀取記憶體中的ram．也就是一種資料竊取的手法，而在網路裡面就是指發生panic的時候，卻從dump資料或是處理到一半的資料竊取到有加密的資料．
    - 所以GoPanic 做的事情相當簡單:
        - 建立一個UDP services
        - 當系統呼叫propietary panic function (ex: do_panic() )，就會呼叫這個 UDP services 去做某些事情．（可能是關閉services或是清除暫存資料...等等)
        - do_panic裡頭呼叫的處理部分需要自己處理．
    - 這個部分可以參考 Python 的[panic_bcast](https://github.com/qnrq/panic_bcast)
        
        

##Toolkit

- [Gohinetradio: Getting hinet online radio url & token and open without adobe flash.](https://github.com/toomore/gohinetradio)         
    - 用Go寫的讀取Hinet Radio 的小工具，寫的人是寫出python擷取台灣上市櫃股票[grs](https://github.com/toomore/grs)的[Toomore](http://blog.toomore.net/)


##OtherGoList

- [Awesome-go](https://github.com/avelino/awesome-go)
    - 相當多Go kit 資訊的列表，本站也是受它啟發．