1.	Leap year program 

package main
import "fmt"
func main() {
	var year int
	fmt.Printf("Enter year: ")
	fmt.Scanf("%d", &year)
	if year%4 == 0 {
			fmt.Println("It is leap year")
	} else {
			fmt.Println("It is not leap year")
	}
}
***************************************************************************************

2.	ATM programme 
package main

import 
	"fmt"
	
var balance float32 = 0
var anoth_Trans int

func transaction() {

	var choice int
	
	fmt.Printf("\nEnter any option \n\n")
    fmt.Printf("1. Withdraw\n")
    fmt.Printf("2. Deposit\n")
    fmt.Printf("3. Balance\n\n")
	fmt.Scan(&choice)

	var amountToWithDraw float32
	var amountToDeposit float32

	switch choice {
		case 1:
			
			fmt.Printf("\nPlease enter amount to withdraw: ")
			fmt.Scan(&amountToWithDraw)

			if amountToWithDraw > balance {
				fmt.Printf("There is no sufficient balance in account")
				fmt.Printf("Do you want another transaction?\nPress 1 to proceed and 2 to exit\n\n")
				fmt.Scan(&anoth_Trans)

				switch anoth_Trans {
					case 1:
						transaction()
					default:
						fmt.Println("\nThanks for using our service!!! \nHave a nice day")
				}
			} else {
				balance -= amountToWithDraw
				fmt.Printf("You have withdrawn %.2f and your new balance is %.2f ", amountToWithDraw, balance)
				fmt.Printf("\n\nDo you want another transaction?\nPress 1 to proceed and 2 to exit\n\n")
				fmt.Scan(&anoth_Trans)

				switch anoth_Trans {
					case 1:
						transaction()
					default:
						fmt.Println("\nThanks for using our service!!! \nHave a nice day")
				}
			}	
		case 2:
			// Deposit
			fmt.Printf("\nPlease enter amount to deposit: ")
			fmt.Scan(&amountToDeposit)

			balance += amountToDeposit

			fmt.Printf("Thank you for depositing, new balance is: %.2f", balance)
			fmt.Printf("\n\nDo you want another transaction?\nPress 1 to proceed and 2 to exit\n\n")
			fmt.Scan(&anoth_Trans)

			switch anoth_Trans {
				case 1:
					transaction()
				default:
					fmt.Println("\nThanks for using our service!!! \nHave a nice day")
			}		
		case 3:
			fmt.Printf("\nYour bank balance is: %.2f", balance)
			fmt.Printf("\n\nDo you want another transaction?\nPress 1 to proceed and 2 to exit\n\n")
			fmt.Scan(&anoth_Trans)

			switch anoth_Trans {
				case 1:
					transaction()
				default:
					fmt.Println("\nThanks for using our service!!! \nHave a nice day")
			}
	}
}
func main() {	
	fmt.Printf("\n Welcome to ATM\n")
	transaction()
}









