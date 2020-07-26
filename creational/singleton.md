# 싱글톤 패턴(Singleton Pattern)

싱글톤 생성 디자인 패턴은 타입의 인스턴스화를 단일 객체로 제한합니다.

## 구현

```go
package singleton

type singleton map[string]string

var (
    once sync.Once

    instance singleton
)

func New() singleton {
	once.Do(func() {
		instance = make(singleton)
	})

	return instance
}
```

## 사용법

```go
s := singleton.New()

s["this"] = "that"

s2 := singleton.New()

fmt.Println("This is ", s2["this"])
// This is that
```

## 경험 법칙(Rules of Thumb)

- 싱글톤 패턴은 전역 상태를 나타내며 대부분의 경우 테스트 가능성이 줄어 듭니다.
