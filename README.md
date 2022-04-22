# Roulette
Game
package main
import (
    "fmt"
    "os"
    "math/rand"
    "time"
)
 
func main() {
    var bid int
    var money int
    var fieldNumber int
    var rouletteNumber int
       money = 10000
    fmt.Print("Рулетка ")
    fmt.Println(money)
    for i := 1; i < 10; i++{
        fmt.Print("Сделай ставку: ")
        fmt.Fscan(os.Stdin, &bid) 
     
        fmt.Print("Номер поля от 1 до 32: ")
        fmt.Fscan(os.Stdin, &fieldNumber)
	    if  fieldNumber > 33 || fieldNumber < 0{
            fmt.Println("Lol")
        } else { 
            rand.Seed(time.Now().UnixNano())
            rouletteNumber = rand.Intn(33)
            if  fieldNumber == rouletteNumber {
                bid = 31*bid
                money = money + bid
            } else {
                money = money - bid
            }
            fmt.Println(money, rouletteNumber)
	    }
    }
}
