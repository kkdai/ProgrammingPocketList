# ProgrammingPocketList

放一些我找到跟程式設計有關的口袋名單，可能是好用的SDK或是其他的．主要用中文寫，我想英文有太多可以參考了． 

內容列表:

- [Golang](#golang)
    - [Database](#database)
    - [Command Line Tools](#command-line-tools)
    - [Network Framework](#network-framework)
    - [Challenge / Testing / Tutorial](#challenge--testing--tutorial)
    - [Error Handle](#error-handle)
    - [Package Management](#package-management)
    - [Toolkit](#toolkit)
    - [Other Go List](#othergolist)
- [iOS](#iOS)
    - [Homekit](#homekit)
    - [Apple Watch](#apple-watch)
- [Android](#android)    
    - [Android UI](#android-ui)
- [Python](#python)
    - [Network](#python-network)
- [Other Tools](#other-tools)
    
## Golang

### Database

- [Collecting data using BigQuery, Elasticsearch, and Go.](http://www.rounds.com/blog/collecting-user-data-and-usage/)
    - Git is [here](https://github.com/rounds/go-bqstreamer).



### Command Line Tools
- [Gore: Yet another Go REPL that works nicely. Featured with line editing, code completion, and more.](https://github.com/motemen/gore)
    - 另外一個Go REPL的工具，支援許多shortcut跟即時顯示...
- [termui: Golang terminal dashboard](https://github.com/gizak/termui)
- [bat: Go implement CLI, cURL-like tool for humans](https://github.com/astaxie/bat)   
    - 可以簡單地在command line 發送http或是其他網路相關的指令．
- [thefuck: Magnificent app which corrects your previous console command.](https://github.com/nvbn/thefuck)
    - 在console mode 打錯指令的時候，只要打出一個 fuck，自動會幫你把正確的指令拼出來．很有趣的點子．

### Network Framework
- [GRPC: Go Project](https://github.com/grpc/grpc-go)
    - GRPC is a google in house RPC client/server project which support 9+ languages. It also support HTTP/2.
    - 支援HTTP/2之外，還支援九種以上的語言．並且可以擺脫net/rpc原本需要管理gob的痛苦．
- [huandu/facebook: A Facebook Graph API SDK Library For Golang](https://github.com/huandu/facebook)
- [Echo: Fast HTTP router + micro web framework 
[http://labstack.github.io/echo](http://labstack.github.io/echo)](https://github.com/labstack/echo)
    - 簡易的router + web framework. HN 有相關討論．
- [http2: HTTP/2 support for Go (in active development)](https://github.com/bradfitz/http2)    
    - 之後會放入Go基本功能的http2開發
    - [h2i is an interactive HTTP/2 ("h2") console debugger. Miss the good ol' days of telnetting to your HTTP/1.n servers? We're bringing you back.](https://github.com/bradfitz/http2/tree/master/h2i)
    

### Challenge / Testing / Tutorial
- [Operation Go](http://gocode.io/)
    - 透過扮演兩個探員的故事，裡面穿插很多Go programing的測驗．
- [Go benchmark competition](http://gobench.org/)
    - 把你的程式碼寫去然後比較誰的效率比較好...
- [Code Jam 2015](https://code.google.com/codejam/distributed_index.html)
    - 可以用任何語言參加科技競賽，不過會被各國好手慘電．
- [GoChallenge](http://golang-challenge.com/)    

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
- [Goworker: goworker is a Go-based background worker that runs 10 to 100,000* times faster than Ruby-based workers.](http://www.goworker.org/)
    - 可以使用這個搭配[heroku](https://github.com/benmanns/goworker-examples)讓你可以在heroku上面跑background task.

- [Seven5: Web blog framework include REST and AJAX conbime in Go](http://seven5.github.io/tutorial.html)
    -  裡面包含如何架設一個blog engine並且支援REST與AJAX( 不需要寫jS).   
- [Go monkeypatching](https://github.com/bouk/monkey)    
- [vault: A tool for managing secrets. 
http://vaultproject.io](https://github.com/hashicorp/vault)
    - 提供許多保護資料的API不論是secretc或是加密的方式．
- [deferpanic:Next Generation Production Systems for the Go Engineer](https://deferpanic.com/)
    - 提供API服務可以監測panic, error handle, memory usage and garbadge collection..  感覺不錯用....
- [expvarmon: TermUI based monitor for Go apps using expvars (/debug/vars). Quickest way to monitor your Go app(s).](https://github.com/divan/expvarmon)
    - 提供一個UI來監控Go App (可以多個)
- [azure-sdk-for-go](https://github.com/Azure/azure-sdk-for-go)    
    - 一些工具讓你可以在使用azure的services
    
### Science 

- [golearn: Machine Learning for Go](https://github.com/sjwhitworth/golearn)

    
### Multimedia 
- [Go-Colorful: A library for playing with colors in go (golang).](https://github.com/lucasb-eyer/go-colorful)
    - 可以做許多color space conversion或是相關的color動作．
- [Azul3d: A 3D game engine written in Go!](http://azul3d.org/)
- [Go SDL2: SDL2 binding for Go](https://github.com/veandco/go-sdl2)
    - Help module to use SDL2 in GO.    
    
### Package Management
- [GPM: Barebones dependency manager for Go.](https://github.com/pote/gpm)
    - look like Ruby RPM package management.
- [bunch: npm-like tool for managing Go dependencies](https://github.com/dkulchenko/bunch)
    - Similar with GPM ruby RPM base.
- [gb, the project based build tool for Go](https://github.com/constabulary/gb)
    - 使用project base的方式來build Go package..     

### Cross Language

- [jvm.go](https://github.com/zxh0/jvm.go)
    - Run .jar file in Golang, it still under implement but I am looking forward it future update.
- [gxui: An experimental Go cross platform UI library.](https://github.com/google/gxui)
    - Written by Googler non-official experimental library for cross platform UI implement.
- [Visual Studio Extension: Go Language Support](https://visualstudiogallery.msdn.microsoft.com/bd7675ba-1bf5-4395-8c5a-4fc19dfc0d76)
- [GoRuby, an implementation of Ruby written in Go](https://github.com/goruby/goruby)
- [go-rpio: Raspberry Pi GPIO library for go-lang](https://github.com/- stianeikeland/go-rpio)
    - 不需要透過C library 可以存取RPI GPIO 

### UI Framework

- [andlabs/ui: Platform-native GUI library for Go](https://github.com/andlabs/ui)
- [go-qml/qml: QML support for the Go language](https://github.com/go-qml/qml)

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

### Go Robot

- [Gobot: Next generation robotics framework with support for 15 different platforms](http://gobot.io/)
    - Golang 機器人framework.    
- [GORT: Robot CLI commands.](http://gort.io/)    
    - CLI command set.
    
### OtherGoList

- [Awesome-go](https://github.com/avelino/awesome-go)
    - 相當多Go kit 資訊的列表，本站也是受它啟發．
- [Resources for new Go programmers](http://dave.cheney.net/resources-for-new-go-programmers)    
    - Dave Cheney summarized Go resource page for newbie
- [Gopher List:A listing of gophers ](https://github.com/gophertown/gophertown-data)        
    - Send a PR if you are gopher...
- [Github: Top Go GitHub developers in Taiwan](http://github-awards.com/users?utf8=%E2%9C%93&type=country&language=Go&country=Taiwan)


### Interesting Go Repro

- [skelterjohn](https://github.com/skelterjohn?tab=repositories)
    - Lots of Go repros which written in Go.

### Go Books

[Build Web Application with Golang](http://astaxie.gitbooks.io/build-web-application-with-golang/content/en/index.html﻿)

    
## iOS

### HomeKit

- [HomeKit Sample in Apple Developer:Catalog](https://developer.apple.com/library/ios/samplecode/HomeKitCatalog/Introduction/Intro.html#//apple_ref/doc/uid/TP40015048)    
- [100 Best Apple HomeKit Videos](http://meta-guide.com/videography/100-best-apple-homekit-videos/)


### Apple Watch

- [Apple Watch Sample in Apple Developer: Lister](https://developer.apple.com/library/prerelease/ios/samplecode/Lister/Introduction/Intro.html)


## Android

### Android-UI

- [Glide: Image Loader Library for Android](https://github.com/bumptech/glide)
    - Introduction and tutorial is [here](http://inthecheesefactory.com/blog/get-to-know-glide-recommended-by-google/en).

## Python

### Python Network

- [pic: ATC (Augement Traffic Control) )](https://github.com/facebook/augmented-traffic-control)
    - Introduction is [here](https://code.facebook.com/posts/1561127100804165/augmented-traffic-control-a-tool-to-simulate-network-conditions/)

## Other tools

- [.bashrc PS1 generator](http://bashrcgenerator.com/)
    - Generate your .bashrc PS1 prompt easily with a drag and drop interface
- [Google: Bazel](http://bazel.io/)   
    - A official Google build tool for Android/iOS and Go.....
    - See [here](https://github.com/google/bazel/tree/master/examples/go) for sameple for Go
- [VS2010: x64dbg](http://x64dbg.com/#start)    
    - Support MSVC2010