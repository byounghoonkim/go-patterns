# 프록시 패턴 (Proxy Pattern)

[프록시 패턴](https://en.wikipedia.org/wiki/Proxy_pattern)은 모든 호출을 가로 채 다른 객체에 대한 액세스를 제어하는 ​객체를 제공합니다.

## 구현

The proxy could interface to anything: a network connection, a large object in memory, a file, or some other resource that is expensive or impossible to duplicate.
프폭시는 네트워크 연결, 메모리 상의 큰 객체, 파일 또는 복제가 불가능하거나 비용이 많이 드는 리소스 등 어떤 것이든 인터페이싱 할 수 있습니다.

간단한 구현 아이디어 :
```go
    // To use proxy and to object they must implement same methods
    type IObject interface {
        ObjDo(action string)
    }

    // Object represents real objects which proxy will delegate data
    type Object struct {
        action string
    }

    // ObjDo implements IObject interface and handel's all logic
    func (obj *Object) ObjDo(action string) {
        // Action behavior
        fmt.Printf("I can, %s", action)
    }

    // ProxyObject represents proxy object with intercepts actions
    type ProxyObject struct {
        object *Object
    }

    // ObjDo are implemented IObject and intercept action before send in real Object
    func (p *ProxyObject) ObjDo(action string) {
        if p.object == nil {
            p.object = new(Object)
        }
        if action == "Run" {
            p.object.ObjDo(action) // Prints: I can, Run
        }
    }
```

## 사용법
More complex usage of proxy as example: User creates "Terminal" authorizes and PROXY send execution command to real Terminal object
보다 복잡한 프록시 사용 예 : 사용자가 "터미널" 권한을 부여하고 PROXY가 실제 터미널 객체에 실행 명령을 보냅니다.
[proxy/main.go](proxy/main.go) 또는 [Playground에서 보기](https://play.golang.org/p/mnjKCMaOVE)를 보세요.
