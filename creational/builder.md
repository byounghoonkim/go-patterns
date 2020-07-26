# 빌더 패턴(Builder Pattern)

빌더 패턴은 동일한 구성 프로세스가 다른 표현을 작성할 수 있도록 복잡한 객체의 구성을 표현과 분리합니다.

Go에서 일반적으로 구성 구조체는 동일한 동작을 저장하는 데 사용되지만, 구조체를 빌더 메소드에 전달하면 보일러 플레이트한 `if cfg.Field! = nil {...}` 검사 코드로 채 웁니다.

## 구현

```go
package car

type Speed float64

const (
    MPH Speed = 1
    KPH       = 1.60934
)

type Color string

const (
    BlueColor  Color = "blue"
    GreenColor       = "green"
    RedColor         = "red"
)

type Wheels string

const (
    SportsWheels Wheels = "sports"
    SteelWheels         = "steel"
)

type Builder interface {
    Color(Color) Builder
    Wheels(Wheels) Builder
    TopSpeed(Speed) Builder
    Build() Interface
}

type Interface interface {
    Drive() error
    Stop() error
}
```

## 사용법

```go
assembly := car.NewBuilder().Paint(car.RedColor)

familyCar := assembly.Wheels(car.SportsWheels).TopSpeed(50 * car.MPH).Build()
familyCar.Drive()

sportsCar := assembly.Wheels(car.SteelWheels).TopSpeed(150 * car.MPH).Build()
sportsCar.Drive()
```
