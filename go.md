## JSON

```go
import (
	"encoding/json"
)

// encode
byteString, err := json.Marshal(myStruct)

// decode string to struct
var st MyStruct = MyStruct{}
err := json.Unmarshal([]byte(myString), &st)
```

Note that the missing fields in `myString` would not cause any error. They just remain the default value; `""` for strings, `0` for ints, and so on. Stupid Go.

## Convert error to string

```go
err.Error()
```

## Reading database query result

```go
var (
	id int
	name string
)
rows, err := db.Query("select id, name from users where id = ?", 1)
if err != nil {
	log.Fatal(err)
}
defer rows.Close()
for rows.Next() {
	err := rows.Scan(&id, &name)
	if err != nil {
		log.Fatal(err)
	}
	log.Println(id, name)
}
err = rows.Err()
if err != nil {
	log.Fatal(err)
}
```

(From [Retrieving Result Sets](http://go-database-sql.org/retrieving.html))

## Lowercase field names for JSON marshaling

```go
type MyStruct struct {
	MyField string `json:"my_field"`
}
```

## Multiple tags for a struct field

```go
type Page struct {
	PageId string				  `bson:"pageId" json:"pageId"`
	Meta   map[string]interface{} `bson:"meta" json:"pageId"`
}
```

(From [How to define multiple name tags in a struct](https://stackoverflow.com/a/18635910))
