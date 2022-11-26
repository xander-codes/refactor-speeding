### Refactoring speeding exercise

format code: ctrl + alt + L  
talk about magic numbers  
```
extract variables for limits in same method:  
    * NO_TICKET_MAX_SPEED,  
    * SMALL_TICKET_MIN_SPEED,  
    * SMALL_TICKET_MAX_SPEED,  
    * BIG_TICKET_MIN_SPEED  
```

change a little bit - test a little bit  

```
change return type of method to int, add elses with -1  
save result to variable and sout the variable
```

```
create class Ticket  
  move variables with limits to it  
  create getTicket(int speed) method  
  move code from else branch in caughtSpeeding()  
  replace code with Ticket instance and call getTicket()  

  extract boolean methods in getTicket()
  ```


```
create class TicketOnBirthday extends Ticket
  create method adjustSpeedLimitsForBirthday()
    int adjustSpeedBy = 5
    add adjustSpeedBy to each limit variable
    create constructor to be able to call adjustSpeedLimitsForBirthday in it
```

```
back on original class
  replace if branch with instance of TicketOnBirthday
  call getTicket on that instance
  observe that we still have code that looks the same
  split Ticket
  move declaration up
  replace ticketOnBirthday var with ticket
  observe that the call is the same on both branches
  move return out of if-else
  change if-else with ternary
```

```
back in Ticket
  on getTicket()
  simplify is-else
  extract magic numbers to fields
```
```
if there is time
  convert the magic number fields into enum

on TicketOnBirthday
  extract adjustSpeedBy variable to class level
```