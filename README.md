# Goland-MAC-OS-setup-short-guide
Goland MAC OS setup short guide

Source http://sourabhbajaj.com/mac-setup/Go/README.html 

….  But some steps are wrong or difficult to use :-) 

    $ brew update

**!!!** see execution log, additional action may be required 
    
    $ brew install golang

    $ sudo nano /etc/profile

**!!!** sudo command is required to make changes in the file



### Edit profile:

    # This is actually your profile file

    export GOPATH=$HOME/YOUR_GO_PROJECT_FOLDER

    # $HOME is the path to your folders (/Users/your_account) ,

    # YOUR_GO_PROJECT_FOLDER is a example name of your go-folder, edit it in your opinion

    export GOBIN=$GOPATH/bin

    export PATH=$PATH:/usr/local/go/bin:$GOBIN



### Start new system variables (without system reboot):

    $ source /etc/profile



### Create the workspace directories tree:

    $ mkdir -p $GOPATH $GOPATH/src $GOPATH/pkg $GOPATH/bin

### Create a file in your $GOPATH/src, in this case hello.go Hello world program :

    package main

    import "fmt"

    func main() {

        fmt.Printf("hello, world\n")
    
    }

### Run your first Go program by executing:

    $ go run $GOPATH/src/hello.go

You'll see a sweet hello, world stdout

If you wish to compile it and move it to $GOPATH/bin, then run:

    $ go install $GOPATH/src/hello.go
 
Since we have $GOPATH/bin added to our $PATH, you can run your program from placement :

    $ hello

Prints : hello, world
