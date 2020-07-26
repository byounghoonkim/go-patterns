# 객체 풀 패턴(Object Pool Pattern)

객체 풀 생성 디자인 패턴은 요청 기대에 따른 여러 인스턴스를 준비하고 유지하는 데 사용됩니다.

## 구현

```go
package pool

type Pool chan *Object

func New(total int) *Pool {
	p := make(Pool, total)

	for i := 0; i < total; i++ {
		p <- new(Object)
	}

	return &p
}
```

## 사용법

아래는 객체 풀의 간단한 수명주기 예제입니다.

```go
p := pool.New(2)

select {
case obj := <-p:
	obj.Do( /*...*/ )

	p <- obj
default:
	// No more objects left — retry later or fail
	return
}
```

## 경험 법칙(Rules of Thumb)

- 개체 풀 패턴은 개체 초기화가 개체 유지 관리보다 비싼 경우에 유용합니다.
- 꾸준한 요청되는것이 아니라 요청이 급증하는 경우 유지 오버 헤드가 오브젝트 풀의 이점을 초과 할 수 있습니다.
- 객체가 미리 초기화되어 성능에 긍정적인 영향을 미칩니다.