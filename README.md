<p align="center">
  <img src="/gopher.png" height="400">
  <h1 align="center">
    Go Patterns
    <br>
    <a href="http://travis-ci.org/tmrts/go-patterns"><img alt="build-status" src="https://img.shields.io/badge/build-passing-brightgreen.svg?style=flat-square" /></a>
    <a href="https://github.com/sindresorhus/awesome" ><img alt="awesome" src="https://img.shields.io/badge/awesome-%E2%9C%93-ff69b4.svg?style=flat-square" /></a>
    <a href="https://github.com/tmrts/go-patterns/blob/master/LICENSE" ><img alt="license" src="https://img.shields.io/badge/license-Apache%20License%202.0-E91E63.svg?style=flat-square" /></a>
  </h1>
</p>

Go 언어에 대한 관용적 디자인 및 응용 프로그램 패턴 모음입니다.

## 생성 패턴 (Creational Patterns)

| Pattern | Description | Status |
|:-------:|:----------- |:------:|
| [추상 팩토리(Abstract Factory)](creational/abstract_factory.md) | 관련 객체 패밀리 생성을 위한 인터페이스 제공| ✘ |
| [빌더(Builder)](creational/builder.md) | 간단한 객체를 이용해 복잡한 객체를 만듬| ✔ |
| [팩토리 메소드(Factory Method)](creational/factory.md) | 객체 인스턴스 생성을 인스턴스 생성을 위한 특수 함수로 지연(defers)| ✔ |
| [객체 풀(Object Pool)](creational/object-pool.md) | 동일 타입의 객체 인스턴스의 그룹을 만들고 유지| ✔ |
| [싱글톤(Singleton)](creational/singleton.md) | 특정 타입을 단일 객체로 인스턴스화 하도록 제한| ✔ |

## 구조 패턴 (Structural Patterns)

| Pattern | Description | Status |
|:-------:|:----------- |:------:|
| [브리지(Bridge)](structural/bridge.md) | 독립적으로 변경 가능하도록 인터페이스를 구현으로 부터 분리 | ✘ |
| [복합(Composite)](structural/composite.md) | 다양한 객체에 대한 액세스를 캡슐화하여 제공 | ✘ |
| [데코레이터(Decorator)](structural/decorator.md) | 객체에 정적 또는 동적 행위를 추가 | ✔ |
| [퍼사드(Facade)](structural/facade.md) | 한 유형을 다른 유형의 API로 사용 | ✘ |
| [플라이웨이트(Flyweight)](structural/flyweight.md) | 자원 사용을 최소화하기 위해 유사 / 동일한 상태의 기존 객체 인스턴스를 재사용 | ✘ |
| [프록시(Proxy)](structural/proxy.md) | 오브젝트의 처리를 제어하는 대리자를 제공 | ✔ |

## Behavioral Patterns

| Pattern | Description | Status |
|:-------:|:----------- |:------:|
| [책임 사슬(Chain of Responsibility)](behavioral/chain_of_responsibility.md) | 더 많은 객체 요청 처리 기회를 송신자와 수신자 커플링 회피 | ✘ |
| [명령(Command)](behavioral/command.md) | 향후 호출할 명령문과 인수를 묶음 | ✘ |
| [중재자(Mediator)](behavioral/mediator.md) | 프록시로 객체와 행동을 연결 | ✘ |
| [메멘토(Memento)](behavioral/memento.md) | 이전 상태로 돌아가는 데 사용할 수있는 불투명 토큰 생성 | ✘ |
| [관찰자(Observer)](behavioral/observer.md) | 이벤트/데이터 변경에 대한 알림을 위한 콜백 제공 | ✔ |
| [Registry](behavioral/registry.md) | Keep track of all subclasses of a given class | ✘ |
| [State](behavioral/state.md) | Encapsulates varying behavior for the same object based on its internal state | ✘ |
| [Strategy](behavioral/strategy.md) | Enables an algorithm's behavior to be selected at runtime | ✔ |
| [Template](behavioral/template.md) | Defines a skeleton class which defers some methods to subclasses | ✘ |
| [Visitor](behavioral/visitor.md) | Separates an algorithm from an object on which it operates | ✘ |

## Synchronization Patterns

| Pattern | Description | Status |
|:-------:|:----------- |:------:|
| [Condition Variable](synchronization/condition_variable.md) | Provides a mechanism for threads to temporarily give up access in order to wait for some condition | ✘ |
| [Lock/Mutex](synchronization/mutex.md) | Enforces mutual exclusion limit on a resource to gain exclusive access | ✘ |
| [Monitor](synchronization/monitor.md) | Combination of mutex and condition variable patterns | ✘ |
| [Read-Write Lock](synchronization/read_write_lock.md) | Allows parallel read access, but only exclusive access on write operations to a resource | ✘ |
| [Semaphore](synchronization/semaphore.md) | Allows controlling access to a common resource | ✔ |

## Concurrency Patterns

| Pattern | Description | Status |
|:-------:|:----------- |:------:|
| [N-Barrier](concurrency/barrier.md) | Prevents a process from proceeding until all N processes reach to the barrier | ✘ |
| [Bounded Parallelism](concurrency/bounded_parallelism.md) | Completes large number of independent tasks with resource limits | ✔ |
| [Broadcast](concurrency/broadcast.md) | Transfers a message to all recipients simultaneously | ✘ |
| [Coroutines](concurrency/coroutine.md) | Subroutines that allow suspending and resuming execution at certain locations | ✘ |
| [Generators](concurrency/generator.md) | Yields a sequence of values one at a time | ✔ |
| [Reactor](concurrency/reactor.md) | Demultiplexes service requests delivered concurrently to a service handler and dispatches them syncronously to the associated request handlers | ✘ |
| [Parallelism](concurrency/parallelism.md) | Completes large number of independent tasks | ✔ |
| [Producer Consumer](concurrency/producer_consumer.md) | Separates tasks from task executions | ✘ |

## Messaging Patterns

| Pattern | Description | Status |
|:-------:|:----------- |:------:|
| [Fan-In](messaging/fan_in.md) | Funnels tasks to a work sink (e.g. server) | ✔ |
| [Fan-Out](messaging/fan_out.md) | Distributes tasks among workers (e.g. producer) | ✔ |
| [Futures & Promises](messaging/futures_promises.md) | Acts as a place-holder of a result that is initially unknown for synchronization purposes | ✘ |
| [Publish/Subscribe](messaging/publish_subscribe.md) | Passes information to a collection of recipients who subscribed to a topic | ✔ |
| [Push & Pull](messaging/push_pull.md) | Distributes messages to multiple workers, arranged in a pipeline | ✘ |

## Stability Patterns

| Pattern | Description | Status |
|:-------:|:----------- |:------:|
| [Bulkheads](stability/bulkhead.md)  | Enforces a principle of failure containment (i.e. prevents cascading failures) | ✘ |
| [Circuit-Breaker](stability/circuit-breaker.md) | Stops the flow of the requests when requests are likely to fail | ✔ |
| [Deadline](stability/deadline.md) | Allows clients to stop waiting for a response once the probability of response becomes low (e.g. after waiting 10 seconds for a page refresh) | ✘ |
| [Fail-Fast](stability/fail_fast.md) | Checks the availability of required resources at the start of a request and fails if the requirements are not satisfied | ✘ |
| [Handshaking](stability/handshaking.md) | Asks a component if it can take any more load, if it can't, the request is declined | ✘ |
| [Steady-State](stability/steady_state.md) | For every service that accumulates a resource, some other service must recycle that resource | ✘ |

## Profiling Patterns

| Pattern | Description | Status |
|:-------:|:----------- |:------:|
| [Timing Functions](profiling/timing.md) | Wraps a function and logs the execution | ✔ |

## Idioms

| Pattern | Description | Status |
|:-------:|:----------- |:------:|
| [Functional Options](idiom/functional-options.md) | Allows creating clean APIs with sane defaults and idiomatic overrides | ✔ |

## Anti-Patterns

| Pattern | Description | Status |
|:-------:|:----------- |:------:|
| [Cascading Failures](anti-patterns/cascading_failures.md) | A failure in a system of interconnected parts in which the failure of a part causes a domino effect | ✘ |
