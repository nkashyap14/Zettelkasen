# Conversions

- Golang does not allow for [[implicit conversions]]
```
//Conversion must be done as such
valueOfTypeB = typeB(valueOfTypeA)

package main
import "fmt"

func main(){
	var number float32 = 5.2
	fmt.Println(number) // prints 5.2
	fmt.Println(int(number)) // prints 5
}
```


---
Links :: [[#Example Code]] [[Computer Science]] 
Reference :: [[Golang]]
Type :: #code
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-10-07 06:26
