# 데코레이터 패턴 (Decorator Pattern)
데코레이터 구조 패턴을 사용하면 내부를 변경하지 않고 기존 객체의 기능을 동적으로 확장 할 수 있습니다.

데코레이터는 객체의 기능을 확장 할 수있는 유연한 방법을 제공합니다.

## 구현
`LogDecorate`는 정수를 조작하는 `func(int) int` 서명의 함수를 장식(decorate)하고 입/출력 로깅 기능을 추가 합니다.

```go
type Object func(int) int

func LogDecorate(fn Object) Object {
	return func(n int) int {
		log.Println("Starting the execution with the integer", n)

		result := fn(n)

		log.Println("Execution is completed with the result", result)

        return result
	}
}
```

## 사용법
```go
func Double(n int) int {
    return n * 2
}

f := LogDecorate(Double)

f(5)
// Starting execution with the integer 5
// Execution is completed with the result 10
```

## 경험 법칙(Rules of Thumb)
- 어댑터 패턴과 달리 장식 할 대상은 **인젝션**으로 얻습니다.
- 데코레이터는 객체의 인터페이스를 변경해서는 안됩니다.
