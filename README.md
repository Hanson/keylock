# keylock
Golang utility class KeyLock: lock by string key, so as to avoid giant lock

`KeyLocker` return `*sync.Mutex` to support `TryLock`

## Usage

```go
kl := keylock.NewKeyLock()

if !kl.KeyLocker("key").TryLock() {
	return
}

kl.Lock(guid)
# do something
kl.Unlock(guid)
```