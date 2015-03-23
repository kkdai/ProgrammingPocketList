# ProgrammingPocketList

放一些我找到跟程式設計有關的口袋名單，可能是好用的SDK或是其他的．主要用中文寫，我想英文有太多可以參考了． 

內容列表:

- [Golang](#golang)
    - [Command Line Tools](#command-line-tools)
    - [Network Framework](#network-framework)
    - [Challenge / Testing / Tutorial](#challenge--testing--tutorial)
    - [Error Handle](#error-handle)
    - [Toolkit](#toolkit)
    - [Other Go List](#othergolist)
    
    
## Golang

### Command Line Tools
- [Gore: Yet another Go REPL that works nicely. Featured with line editing, code completion, and more.](https://github.com/motemen/gore)
    - 另外一個Go REPL的工具，支援許多shortcut跟即時顯示...

### Network Framework
- [GRPC: Go Project](https://github.com/grpc/grpc-go)
    - GRPC is a google in house RPC client/server project which support 9+ languages. It also support HTTP/2.
    - 支援HTTP/2之外，還支援九種以上的語言．並且可以擺脫net/rpc原本需要管理gob的痛苦．


### Challenge / Testing / Tutorial
- [Operation Go](http://gocode.io/)
    - 透過扮演兩個探員的故事，裡面穿插很多Go programing的測驗．

### Error Handle

- [Golang] [GoPanic](https://github.com/joedborg/gopanic) Panic 是Go裡面一個發生錯誤會呼叫的函式，其實只是做memory dump而以．但是為了避免Panic 發生的時候，一些資料被竊取． 
    - [Cold Boot Attack](http://en.wikipedia.org/wiki/Cold_boot_attack):原本指的是加密的key寫在記憶體，卻被冷卻後移除電腦而直接讀取記憶體中的ram．也就是一種資料竊取的手法，而在網路裡面就是指發生panic的時候，卻從dump資料或是處理到一半的資料竊取到有加密的資料．
    - 所以GoPanic 做的事情相當簡單:
        - 建立一個UDP services
        - 當系統呼叫propietary panic function (ex: do_panic() )，就會呼叫這個 UDP services 去做某些事情．（可能是關閉services或是清除暫存資料...等等)
        - do_panic裡頭呼叫的處理部分需要自己處理．
    - 這個部分可以參考 Python 的[panic_bcast](https://github.com/qnrq/panic_bcast)                
- [Managing Application Shutdown in Go](http://vrecan.github.io/post/golang_shutdown/) 
    - cool pkg... call  "death"

### Toolkit

- [Gohinetradio: Getting hinet online radio url & token and open without adobe flash.](https://github.com/toomore/gohinetradio)         
    - 用Go寫的讀取Hinet Radio 的小工具，寫的人是寫出python擷取台灣上市櫃股票[grs](https://github.com/toomore/grs)的[Toomore](http://blog.toomore.net/)
- [Viper: A configuration tool of Go](http://spf13.com/project/viper)
    - 用來讀取與使用Config的工具，開發者是[spf13](http://spf13.com/) [Hugo](http://spf13.com/project/hugo)的開發者．當然，[Hugo](http://spf13.com/project/hugo)也有使用[Viper](http://spf13.com/project/viper)
- [Russ Cox: Regxp code search in Go](http://swtch.com/~rsc/regexp/regexp4.html)
    - 有人拿來用說接近2GB的code search竟然也有200ms的速度．相當的恐怖啊．

### Cross Language

- [jvm.go](https://github.com/zxh0/jvm.go)
    - Run .jar file in Golang, it still under implement but I am looking forward it future update.
- [gxui: An experimental Go cross platform UI library.](https://github.com/google/gxui)
    - Written by Googler non-official experimental library for cross platform UI implement.

### Meetups

- [Youtube Playlist: London Go Gathering February 2015](https://www.youtube.com/playlist?list=PLtLJO5JKE5YCZYDAt8-uyJbVgq1FIUpVM)
- [FOSDEM 2015 Video list](http://video.fosdem.org/2015/devroom-go/)
    - Go at CoreOS by +Kelsey Hightower​​
        - This session will discuss using Go to build products that make distributed computing as stress-free as installing a Linux distribution.
    - Finding Bad Needles in Worldwide Haystacks by Dmitry Savintsev
        - Experience of using Go for a large-scale web security scanner
    - Moving MongoDB components to Go by +Norberto Leite​​ 
        - We love Go and this train is unstoppable!  
    - CockroachDB by +Tobias Schottdorf​​  
        - Towards an Open-Source Spanner	
    - HTTP/2 for Go by +Brad Fitzpatrick​​ 
        - Overview of HTTP/2 and the design of Go's support for it
    - Go and the modern enterprise by +Peter Bourgon​​ 
    - bleve - text indexing for Go by +Marty Schoch​​ 
    - The State of Go by +Andrew Gerrand​​ 
    - Go Lightning Talks by +Andrew Gerrand​​ 
        - The Go community on Go﻿
- [Youtube: FOSDEM 2015 Go present playlist](https://www.youtube.com/playlist?list=PLtLJO5JKE5YDK74RZm67xfwaDgeCj7oqb)
    - 關於Golng 有關的session集合，總而言之還是HTTP/2跟Go 1.5   
    
    
### OtherGoList

- [Awesome-go](https://github.com/avelino/awesome-go)
    - 相當多Go kit 資訊的列表，本站也是受它啟發．
    
    
## iOS

### HomeKit

- [HomeKit Sample in Apple Developer:Catalog](https://developer.apple.com/library/ios/samplecode/HomeKitCatalog/Introduction/Intro.html#//apple_ref/doc/uid/TP40015048)    
- [100 Best Apple HomeKit Videos](http://meta-guide.com/videography/100-best-apple-homekit-videos/)


### Apple Watch

- [Apple Watch Sample in Apple Developer: Lister](https://developer.apple.com/library/prerelease/ios/samplecode/Lister/Introduction/Intro.html)


## Other tools

- [.bashrc PS1 generator](http://bashrcgenerator.com/)
    - Generate your .bashrc PS1 prompt easily with a drag and drop interface