# 팩토리 메소드 패턴(Factory Method Pattern)

팩토리 메소드 작성 디자인 패턴을 사용하면 작성 될 오브젝트의 정확한 유형을 지정하지 않고도 오브젝트를 작성할 수 있습니다.

## 구현

예제 구현은 인-메모리, 디스크 스토리지 등 다른 백엔드의 데이터 저장소를 제공하는 방법을 보여줍니다.

### 타입

```go
package data

import "io"

type Store interface {
    Open(string) (io.ReadWriteCloser, error)
}
```

### 다른 구현

```go
package data

type StorageType int

const (
    DiskStorage StorageType = 1 << iota
    TempStorage
    MemoryStorage
)

func NewStore(t StorageType) Store {
    switch t {
    case MemoryStorage:
        return newMemoryStorage( /*...*/ )
    case DiskStorage:
        return newDiskStorage( /*...*/ )
    default:
        return newTempStorage( /*...*/ )
    }
}
```

## 사용법

팩토리 메소드를 사용하면 사용자가 원하는 스토리지 유형을 지정할 수 있습니다.

```go
s, _ := data.NewStore(data.MemoryStorage)
f, _ := s.Open("file")

n, _ := f.Write([]byte("data"))
defer f.Close()
```
