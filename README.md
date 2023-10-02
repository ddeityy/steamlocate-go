# steamlocate

A (worse) go version of [steamlocate-rs](https://github.com/WilliamVenner/steamlocate-rs) which locates any Steam application on the filesystem, and/or the Steam installation itself.

**This library only supports Linux for now.**

## Using steamlocate
Download:
```console
$ go get -u github.com/Ddeityy/steamlocate-go
```

##TODO
* Doc-comments
* Shortcuts (non-steam games)
* Steam compatibility tools (proton)

## Examples

#### Locate the installed Steam directory

```go
import "github.com/Ddeityy/steamlocate-go"

var s steamlocate.SteamDir

s.Locate()

fmt.Println(s.Path)
```
```go
SteamDir {
    Path string: "/home/$USER/.steam/steam"
}
```

#### Locate all installed Steam apps or a specific one by it's app ID

```go
import "github.com/Ddeityy/steamlocate-go"

var s steamlocate.SteamDir

s.Locate()

fmt.Println(s.SteamApps.Apps)

fmt.Println(s.SteamApps.Apps[440].Name)

```
```go
Apps {
    440: {
    ID int: 440 
    Path string: /home/deity/.steam/steam/steamapps/common/Team Fortress 2
    Name string: Team Fortress 2}
    ...
}
```

#### Locate all Steam library folders
```go
import "github.com/Ddeityy/steamlocate-go"

var s steamlocate.SteamDir

s.Locate()

fmt.Println(s.LibraryFolders.Paths)
```
```go
{
    "/home/$USER/.steam/steam/steamapps"
    "/home/$USER/second_drive/steam/steamapps"
    ...
}
```
