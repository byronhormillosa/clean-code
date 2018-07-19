#### Questions
>1. In your own words, explain what clean code is and why it is important.

A: 

Team collaboration - code must be written in such a manner that it can be read efficiently. If you are not writing understandable code you will be wasting the entire team's development time in solving conflicts, understanding logic flow, diffing and merging.

Maintainability - this is where reinforcing single responsibility principle comes in handy. The principle stipulates that every function and class should have only one responsibility. The idea is to treat each function or class as modular components. It will be easier to alter class propeties or manipulating function conditions as an application progresses.

Accountability -writing code entails producing content. Content that describes who we are as professionals. Writing sloppy code with improper indentation and nests that are more than two levels deep eventually becomes double work when we reach a project milestone and the code needs refactoring. Writing clean code fosters overall satisfaction and ensures quality of work. Code it once, code it right. Don't repeat yourself.

> 2. Read this article about Toyota and their use of bad code. Although you may not yet understand all of the topics discussed, think about another commonly used object that relies on computers and explain what would happen if the code was not created to an acceptable standard.

A:

When we think of any type of energy consuming equipment that we use on a daily basis in residential and commercial locations such as air conditioning, laundry machines, refrigeration and kitchen appliances we know for a fact that we need electrical power. 

Electrical power derived from a generating source may it be from renewable energy or fossil fuels are all distributed by power plants. This process of distribution are controlled by rugged industrial computers called Programmable Automated Controllers or PAC's. PAC's are programmed using high level programming languages such as Python to make sure critical infrasturcture such as power plants run safely and efficiently.

The principles of clean coding also apply to programming Python. Just like other high level programming languages such as Java, C++ and Ruby, Python also provides a means of creating functions and classes. 

In creating clean code, we implement Single Responsibility Principle to make sure that functions and classes have only one responsibility. Improper composition of creating too many subclasses within a class in attempts to add properties to a class may be in conflict with other parts of code. Class expressions should have their own unique definitions.

This also applies to function declarations in which functions should have specific definitions.  Extracting methods simplifies and modularizes functions. This allows us to see functions as components with specific purposes. When we organize functions as parts of an overall application, we put ourselves in a position where we can easily debug and maintain the code if needed. 

Organizing naming conventions also promotes clean code writing. We setup ourselves for success and maintain consistency by following proper naming conventions for variables, objects, functions, parameters and arguements.

One can only imagine the nightmare scenario where sloppy coding is committed. Think of a scenario for instance critical electric power is shutdown due to a faulty application that manages the efficiency of a generator. If an application cannot be debbuged immediately, the power plant operators cannot get the generator to run leaving an entire town without electricity. 

Residential neighborhoods can probably handle such situations without much of a hassle but think about vital institutions that need electricity. Hospitals, manufacturing facilities, commercial establishments, schools, law enforcement facilities and even places of recreation. Without electrical power to the grid, all of these places are exposed to potential safety risks and financial loses. 

>3. Would you consider the following to be clean code? Explain why or why not. If not, refactor the code.

A:

Code needs to be refactored to enforce proper naming conventions to specifically identify variables.

```JS
FUNCTION do(temperature, units)            
// Creating a new function, set paramenters
  IF units = "F" THEN                         
 // Check if y is equal "F"
    SET result to (temperature−32) * (5/9)     
 // Formula to convert degrees fahrenheit to celsius
    PRINT result                       // Print result

  ELSE IF unitForTemp = "C" THEN          
 // If y not equal to "F", check if equal to "C"
    SET result to x * 1.8000 + 32.00   
 // Formula to convert degrees celsius to fahrenheit
    PRINT result                       
 // Print result

  END IF
END FUNCTION

```

>4. Would you consider the following to be clean code? Explain why or why not. If not, refactor the code.


A:

Added comments to important code steps for better documentation.

```JS
FUNCTION calcPercent(sum, total)            //function to calculate percent with 2 parameters
 IF NOT(total = 0) THEN
     SET percentage to sum / total * 100    //Calculate for percentage
 ELSE
   PRINT "Sorry, cannot divide by 0"        //Expected output, if total = 0
 END IF

 PRINT percentage                           //Result
END FUNCTION

```

>5. Using pseudocode, refactor the code for the following examples using the principles you have learned in this checkpoint.

>a. The following function prints the subtotal of a customer's transaction and receives payment accordingly.

```JS
FUNCTION checkOutCustomer(subTotal, discountRate,tax)
//added tax as a papameter, removed paymentType. Function will only handle amount due

  PRINT "Your total due is: " + subTotal * discountRate + (subTotal * tax)
//display concatenated phrase with amount due 

END FUNCTION
   
   FUNCTION transaction(paymentType)
   //Extracted method, created function to specifically perform transaction type based on payment method
   
   IF paymentType = 'CASH' THEN
   //Initial condition if payment rendered in cash

       CALL getPayment RETURNING amount
       PRINT "Change due: " + amount - subTotal * discountRate + (subTotal * tax)
       //display concatenated phrase with amount due based on cash payment 
   

   ELSE IF paymentType = 'CREDIT CARD' THEN
   //Alternate condition if payment rendered in cash

       CALL getPayment RETURNING amount
       PRINT "Your credit card has been charged: " + subTotal * discountRate + (subTotal * tax)
       //display concatenated phrase with amount due based on Credit Card payment
   
   END IF
END FUNCTION
```
>b. The following function checks out a book if there are no issues with the guest's account.

A:
```JS
FUNCTION checkoutBook(guest)
 IF guest.isAccountActive THEN                                                //renamed account active to isAccountActive to emphasize expected boolean function return
  PRINT 

     IF ((guest.hasOverdueBooks===0) && (guest.outstandingFees=== 0)) THEN    //combined logic to simplify cascading IF statement
       APPEND book to guest.books
         SET book.status to "Checked Out"
           PRINT "Your books have been issued."
     END IF
       ELSE
         PRINT "Unable to check out book."
     END IF
END FUNCTION
```

>c. The following class is a code snippet that should support the transactions a customer can perform at an ATM.

```JS

CLASS BankAccountCheckBalance            //renamed class to uniquely specify its sole purpose 

 FUNCTION displayBalance
    PRINT balance
 END FUNCTION

CLASS BankAccountTransactionDeposit             //Sole purpose of class is to create deposits 

 FUNCTION deposit(amount)
    SET balance to balance + amount
 END FUNCTION

CLASS BankAccountTransactionWithdraw        //Sole purpose of class is to render withdrawals

 FUNCTION withdraw(amount)               
     IF balance > amount THEN
       SET balance to balance - amount
     END
 END FUNCTION

CLASS BankAccountPromotions               //Performs credit card offer

 FUNCTION creditCardOffer
     IF NOT(customer.hasCreditCard) THEN
         CALL offerCreditCard
     END
 END FUNCTION

CLASS BankCheckStatus                     //Verifies checking account

 FUNCTION checkStatus
     IF NOT(customer.hasCheckingAccount) THEN
         CALL offerCheckingAccount
     END
 END FUNCTION

 ....
 ....
 ....

END

```

>6. Square Given an array of integers, find out whether the sum of the integers is a perfect square. If it is a perfect square, return the square root, otherwise return the sum.

A:

```JS
var sampleIntegers = [10, 1, 4, 6, 1, 1, 2]; //Sample array

function squareTest(sampleIntegers) {        //defined function to take array and return number value
  var total = 0;

  for (var i = 0; i < sampleIntegers.length; i++) {
    total += sampleIntegers[i];
                                            //loop to iterate array, calculate sum of elements
}
  var perfectSquare = Math.sqrt(total);     //find square root of total

  if ((total % perfectSquare) === 0) {      //condition to check for perfect square
    return perfectSquare;
  } else {
    return total;                           //alternate condition, sum of sampleIntegers
  }

}

console.log(squareTest(sampleIntegers));
```

>7. Duplicate Given an array of integers, find out whether the array contains any duplicate elements. The function should return true if any value appears at least twice in the array, and false if every element is distinct.

A:

```JS
var sampleIntegers = [2,1,2,3]; 
function checkDuplicates(sampleIntegers) {
    var plot = {}, i, size;

    for (i = 0, size = sampleIntegers.length; i < size; i++){
        if (plot[sampleIntegers[i]]){
            return false;
        }

        plot[sampleIntegers[i]] = true;
    }

    return true;
}
console.log(checkDuplicates(sampleIntegers));
```