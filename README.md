Omdb API in Golang
=======

***
Usage
-------------
The API usage is very simple.

```go
package main

import (
	"fmt"
	"github.com/null-none/gomdbapi"
)

func main() {
	api := gomdb.Init(YOUR_API_KEY)
	
	query := &gomdb.QueryData{Title: "Macbeth", SearchType: gomdb.MovieSearch}
	res, err := api.Search(query)
	if err != nil {
		fmt.Println(err)
		return
	}
	fmt.Println(res.Search)

	query = &gomdb.QueryData{Title: "Macbeth", Year: "2015"}
	res2, err := api.MovieByTitle(query)
	if err != nil {
		fmt.Println(err)
		return
	}
	fmt.Println(res2)

	query = &gomdb.QueryData{Title: "Rick and Morty", Season: "1", Episode: "8", SearchType: gomdb.EpisodeSearch}
	res3, err := api.MovieByTitle(query)
	if err != nil {
		fmt.Println(err)
		return
	}
	fmt.Println(res3)
}
```
