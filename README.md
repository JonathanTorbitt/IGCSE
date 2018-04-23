# IGCSE
For all things IGCSE Practical Programming related

This is where I am storing my C# code for the IGCSE task for summer 2018. When reading this I assume that you already have a copy of the pre-release otherwise this will make little sense to you.

Note:

The solution is a crap one for real life. Do not contact me with comments like 'you should use functions'. There is no requirement for functions in the IGCSE 0478 spec so they have not been used here. This is aimed at the average student who will base their learning and revision directly off the spec document.

Here is some pseudocode. Not perfect by any stretch but not far off. There is some interpreation (to say the least) about some of the niggly points in the questions and I know that I will interpret them completely differently to other people. That's fine. I will make changes to this when I get the chance and make it better.



PSEUDOCODE (code is slightly modified so this is not an exact finished solution):

YOU NEED TO VIEW THIS IN RAW TO READ IT MORE EASILY!!!



 DECLARE computerComponent : ARRAY[0: 12 ] OF STRING { "p3" , "p5", "p7" , "16GB", "32GB" , "1TB", "2TB" , "19' " , "23' " , "mini tower" , "midi tower" , "2 ports" , "4 ports"}  
DECLARE componentPrice : ARRAY [ 0:12] OF INTEGER { 100 , 200 , 300 , 75 , 150 , 50 ,100, 65 , 120 , 40 , 70, 75, 150 }  
DECLARE stockLevels : ARRAY [0:12] OF INTEGER { 15, 22, 7, 2, 0 ,100 , 73 , 50 , 99, 21 , 18 , 85 , 36}  
DECLARE componentChosen : ARRAY [0:5] OF STRING   
DECLARE priceChosen: ARRAY[0:5] OF INTEGER 
DECLARE componentSold: ARRAY [0:13] OF INTEGER  
  
STRING processorChoice <-- ""  
STRING RAMChoice <-- ""  
STRING storageChoice <-- ""  
STRING screenChoice <-- ""  
STRING caseChoice <-- ""  
STRING USBChoice <-- ""  
BOOLEAN processorOrdered <-- FALSE  
BOOLEAN RAMOrdered <-- FALSE  
BOOLEAN storageOrdered <-- FALSE  
BOOLEAN screenOrdered <-- FALSE  
BOOLEAN caseOrdered <-- FALSE  
BOOLEAN USBOrdered <-- FALSE  
  
INTEGER total <-- 0  
DECIMAL finalPrice <--  0  
STRING name <-- ""  
INTEGER userID <-- ""  
STRING answer  
INTEGER numberOfOrders ß 0 
DECIMAL orderValue ß 0 
  
// alternative = WHILE DateTime < “12:00:00” 
  
OUTPUT "Welcome to PCS4U, if you would to start ordering your computer components please enter YES” 
answer ß USERINPUT 
  
WHILE answer = “YES” DO  
  
OUTPUT" Please enter your full name "  
Name <-- USERINPUT  
//assigns user with unique estimate number  
    
SET rand TO CALL random_number_generator_function(1, 100000)   
OUTPUT " Your unique estimate number is " + rand   
  
//user inputs processor choice which is validated  
  
REPEAT   
   OUTPUT "please enter whether you would like a p3, p5 or p7 processor"   
   processorChoice <-- USER INPUT  
    FOR INT i = 0 TO 2 DO  
      IF computerComponent[i] = processorChoice THEN  
         IF stockLevels[i] > 0 THEN  
           total <-- total + componentPrice[i]  
           componentChosen[0] <-- computerComponent[i]  
           priceChosen[0]ßcomponentPrice[i] 
           ProcessorOrdered <-- TRUE  
           stockLevels[i]— 
           componentSold[i]++ 
           i=3  
         ELSE   
            OUTPUT "Sorry not in stock, please choose another model"  
             i=3 
          END IF  
       ELSE IF processorChoice != computerComponent[i+1] && processorChoice !=   computerComponent [i+2] 
          OUTPUT "Sorry we don't stock that model, please choose only from the 3 available p3, p5 or p7"  
          i=3 
     END IF  
  END FOR  
UNTIL processorOrdered <-- TRUE  
  
  
//user inputs RAM choice which is validated  
  
REPEAT   
   OUTPUT "please enter whether you would like a 16GB RAM or 32GB RAM"   
   RAMChoice <-- USER INPUT  
    FOR INT i = 3 TO 4 DO  
      IF computerComponent[i] = RAMChoice THEN  
         IF stockLevels[i] > 0 THEN  
            total <-- total + componentPrice[i]  
            componentChosen[1] <-- computerComponent[i]  
            priceChosen[1]ßcomponentPrice[i] 
            RAMOrdered <-- TRUE  
            stockLevels[i]— 
            componentSold[i]++ 
            i=5 
         ELSE   
             OUTPUT "Sorry not in stock, please choose another model"  
             i=5 
          END IF  
       ELSE IF RAMChoice != computerComponent[i+1]  
          OUTPUT "Sorry we don't stock that model, please choose only from the two available 16GB or 32GB"  
           i=5 
     END IF  
  END FOR  
UNTIL RAMOrdered <-- TRUE  
  
//user inputs storage choice which is validated  
  
REPEAT   
   OUTPUT "please enter whether you would like a 1TB storage or a 2TB storage"   
   storageChoice <-- USER INPUT  
    FOR INT i = 5 TO 6 DO  
      IF computerComponent[i] = storageChoice THEN  
         IF stockLevels[i] > 0 THEN  
            total <-- total + componentPrice[i]  
            componentChosen[2] <-- computerComponent[i]  
            priceChosen[2]ßcomponentPrice[i] 
            storageOrdered <-- TRUE  
            stockLevels[i]— 
            componentSold[i]++ 
            i=7 
         ELSE   
             OUTPUT "Sorry not in stock, please choose another model"  
             i=7 
         END IF  
       ELSE IF storageChoice != computerComponent[i+1]  
          OUTPUT "Sorry we don't stock that model, please choose only from the 2 available 1TB or 2TB"  
          i=7 
     END IF  
  END FOR  
UNTIL storageOrdered <-- TRUE  
  
//user inputs screen choice which is validated  
  
REPEAT   
   OUTPUT "please enter whether you would like a 19' screen or a 23' screen"   
   screenChoice <-- USER INPUT  
    FOR INT i = 7 TO 8 DO  
      IF computerComponent[i] = screenChoice THEN  
         IF stockLevels[i] > 0 THEN  
             total <-- total + componentPrice[i]  
             componentChosen[3] <-- computerComponent[i]  
             priceChosen[3]ßcomponentPrice[i] 
             screenOrdered <-- TRUE  
             componentSold[i]++ 
             stockLevels[i]— 
             i=9 
         ELSE   
                OUTPUT "Sorry not in stock, please choose another model"  
                i=9 
         END IF  
       ELSE IF screenChoice != computerComponent[i+1]  
          OUTPUT "Sorry we don't stock that model, please choose only from the 2 available 19 inch or 23 inch"  
       i=9 
     END IF  
  END FOR  
UNTIL screenOrdered <-- TRUE  
  
//user inputs case choice which is validated  
  
REPEAT   
   OUTPUT "please enter whether you would like a mini tower or a midi tower"   
   caseChoice <-- USER INPUT  
    FOR INT i = 9 TO 10 DO  
      IF computerComponent[i] = caseChoice THEN  
         IF stockLevels[i] > 0 THEN  
            total <-- total + componentPrice[i]  
            componentChosen[4] <-- computerComponent[i]  
            priceChosen[4]ßcomponentPrice[i] 
            ramOrdered <-- TRUE  
            stockLevels[i]— 
            componentSold[i]++ 
            i=11 
         ELSE   
            OUTPUT "Sorry not in stock, please choose another model"  
            i=11 
         END IF  
      ELSE IF caseChoice != computerComponent[i+1]  
          OUTPUT "Sorry we don't stock that model, please choose only from the 2 available mini or midi"  
          i=11 
     END IF  
  END FOR  
UNTIL caseOrdered <-- TRUE  
  
//user inputs USB choice which is validated  
  
REPEAT   
   OUTPUT "please enter whether you would like a 2 ports or 4 ports USB "   
   USBChoice <-- USER INPUT  
    FOR INT i = 11 TO 12 DO  
      IF computerComponent[i] = USBChoice THEN  
         IF stockLevels[i] > 0 THEN  
            total <-- total + componentPrice[i]  
            componentChosen[5] <-- computerComponent[i] 
            priceChosen[5]ßcomponentPrice[i]  
            USBOrdered <-- TRUE  
            stockLevels[i]— 
            componentSold[i]++ 
            i=13 
         ELSE   
                OUTPUT "Sorry not in stock, please choose another model"  
                i=13 
         END IF  
       ELSE IF USBChoice != computerComponent[i+1]  
          OUTPUT "Sorry we don't stock that model, please choose only from the 2 available 2 ports or 4 ports"  
           i=13 
     END IF  
  END FOR  
UNTIL USBOrdered <-- TRUE  
  
//total price of computer is calculated with 20% added on top  
finalPrice <-- total * 1.2  
OUTPUT “----------------------------------------------” 
  
//the summary of order is outputted for the customer and then the shop 
FOR a= 0 TO 1 DO  
    IF a = 0 THEN  
       OUTPUT “Customer’s order copy:” 
       OUTPUT “name: ” + name + “, estimate number: ” + userID + “, date” +dateToday 
       FOR int i=0 TO 5 
          OUTPUT componentChosen[i] + “: £” + priceChosen[i] 
       END FOR 
       OUTPUT “total cost of computer: £” + finalPrice 
   ELSE 
      OUTPUT “Shop’s order copy:” 
      OUTPUT “name: ” + name + “, estimate number: ” + userID + “, date” +dateToday 
       FOR int i=0 TO 5 
          OUTPUT componentChosen[i] + “: £” + priceChosen[i] 
       END FOR 
       OUTPUT “total cost of computer: £” + finalPrice 
END IF 
END FOR  
  
numberOfOrders++ 
orderValueß orderValue+ finalPrice 
Console.Clear 
  
  
//restart the loop 
processorOrdered = FALSE 
RAMOrdered = FALSE 
storageOrdered = FALSE 
screenOrdered = FALSE 
caseOrdered = FALSE 
USBOrdered = FALSE 
  
  
  
OUTPUT “----------------------------------------------” 
OUTPUT “Welcome to PCS4U, if you would to start ordering your computer components please enter YES” 
answerßUSERINPUT 
  
END WHILE  
  
//end of the day summary is outputted  
OUTPUT “----------------------------------------------” 
OUTPUT “End of day summary : ” 
OUTPUT “number of orders made = ” + numberOfOrders 
OUTPUT “the total number of each component sold will be listed in order of processor, RAM, storage, screen, case and USB Ports” 
  
FOR int b = 0 TO 12 DO 
   OUTPUT b + “.” + componentSold[b]  
END FOR 
  
OUTPUT “the value of all orders = £”   + orderValue


