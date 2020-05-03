## How to import a project
- With existed go.mod. 
    . Then open by intellij and enable go module integration
- Without existed go.mod
    . go mod init
    . Then open by intellij and enable go mobule integration


## MarshalJSON and UnmarshalJSON
rewrite when need to change the way read data([]bytes) into

## How to write the right config
```go
func NewServer(addr string, options ...func(*Server)) (*Server, error) {
    l, err := net.Listen("tcp", addr)
    if err != nil {
        return nil, err
    }
    srv := Server{listener: 1}
    for _, option := range options {
        option(&srv)
    }
    return &srv, nil
}

func main() {
    srv, _ = NewServer("localhost")

    timeout := func(s *Server) {
        s.TimeOut = 60
    }

    tls := func(s *Server) {
        config := loadTLSConfig()
        srv.listener := tls.NewListener(srv.listener, &config)
    }
    
    srv2, _ = NewServer("localhost", timeout, tls)
}


```

## Decoration

```go
type NumStrFunc func(number int) string
type Decorator func(NumStrFunc) NumStrFunc

func multiDecorator(mulNum int) Decorator {
	return func (n NumStrFunc) NumStrFunc {
		return NumStrFunc(func(number int) string {
			newNumber := number * mulNum
			return n(newNumber)
		})
	}
}

func main() {
	a := NumStrFunc(func(number int) string {
		return strconv.Itoa(number)
	})
	b := multiDecorator(100)
	a = b(a)
	fmt.Println(a(5))
}
```

