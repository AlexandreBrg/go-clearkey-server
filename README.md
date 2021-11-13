# DRM ClearKey Server

The idea behind this little project is to have a working ClearKey server for test purposes. This was the idea
behind the real first version, but I ended up with a new version of this project written with hexagonal 
architecture in mind. If you don't know what ClearKey systems are, I let you check what is a 
[DRM](https://www.fortinet.com/resources/cyberglossary/digital-rights-management-drm) first, then look for this kind 
of system. Of course, this server is completely compliant with [W3C](https://www.w3.org/TR/encrypted-media/#clear-key) 
specification.

As this is my first application in Go & with this kind of architecture, it is obvious that it is not production ready.

## Usage

As for now there isn't any configuration customization available, you can only run the project and it will listen
onto `:8080` port.

```shell
go run .
```

## Routes

| Method | Route | Description |
| ------ | ----- | ----------- |
| POST | /license |  Request a license value following [W3C](https://www.w3.org/TR/encrypted-media/#clear-key-request-format) specs |
| POST | /license/register | Request to register a new license, no body expected, but it will generate a key that will be returned as [license format](https://www.w3.org/TR/encrypted-media/#clear-key-license-format) |

