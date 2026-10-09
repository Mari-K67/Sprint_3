# Sprint_3
Creating methods.

Class `OnlineSalesRegisterCollector`. It is responsible for the operation of an online cash register.  
The class contains:
* a list `name_items` with a list of items in the receipt;
* a variable `number_items` with the number of items in the receipt;
* a dictionary `item_price`, which lists the store's items and their cost;
* a dictionary `tax_rate`, which records the tax rate on goods. It is 10% or 20% of the cost.

The task is to add methods to the class. Of them — eight required and one additional.

## 1. Write getters.
In the receipt, item names and quantities are printed. But the attributes `name_items` and `number_items` are private. They cannot be accessed directly.  
Write getters that get the values of `name_items` and `number_items`. Use the `@property` decorator.

## 2. Add an item to the receipt.
Write a method `add_item_to_cheque`. It adds items to the receipt.  
As an argument, the method takes the name of the item — `name`.  
In the method body, write conditions:
* If the item name has 0 or more than 40 characters, a `ValueError` exception is raised. It prints the message: 'Нельзя добавить товар, если в его названии нет символов или их больше 40'.
* If the item name is not in the `item_price` list, a `NameError` exception is raised with the text 'Позиция отсутствует в товарном справочнике'.

In all other cases, the method adds the item to `name_items` and increases the value of `number_items` by 1.

## 3. Delete an item from the receipt.
Write a method `delete_item_from_check`. It removes items from the receipt. The method takes a `name` argument.  
In the body, use a condition:
* If the item is not in the `name_items` list, a `NameError` exception is raised with the text 'Позиция отсутствует в чеке';

In all other cases, the method removes the item from `name_items` and decreases `number_items` by 1.

## 4. Calculate the total cost of items.
Write a method `check_amount`. It calculates the total purchase amount.  
The logic is as follows: the method contains an empty list `total` and adds prices of items from the `name_items` list to it. It takes them from the `item_price` dictionary.  
There is also a condition in the method:
* If the receipt has more than 10 items, the receipt amount is returned with a 10% discount;
  
In all other cases, the full amount is returned.

## 5. Calculate VAT for items with a 20% rate.
Write a method `twenty_percent_tax_calculation`. It calculates the VAT for items with a 20% tax rate.  
In the method body:
* Empty list `twenty_percent_tax`. The method adds items from the `name_items` list to it if they have a 20% tax rate in the `tax_rate` dictionary.
* Empty list `total`. The method adds prices of items that were included in `twenty_percent_tax`.

The method should return the total VAT amount for receipt items with the maximum rate.  
Use the formula: VAT = item cost * 0.2.  
When calculating, do not forget to take into account the discount when the number of items is greater than 10.

## 6. Calculate VAT for items with a 10% rate.
Write a method `ten_percent_tax_calculation`. It calculates the VAT for items with a 10% tax rate.  
In the method body:
* Empty list `ten_percent_tax`. The method adds items from the `name_items` list to it if they have a 10% tax rate in the `tax_rate` dictionary.
* Empty list `total`. The method adds prices of items that were included in `ten_percent_tax`.

The method should return the total VAT amount for receipt items with a 10% rate.  
Use the formula: VAT = item cost * 0.1.  
When calculating, do not forget to take into account the discount when the number of items is greater than 10.

## 7. Calculate the total amount of taxes.
Write a method `total_tax`. It returns the total VAT on the receipt.

## 8. Return the customer's phone number.
Write a static method `get_telephone_number`. It returns the customer's phone number.  
The method takes an argument `telephone_number` as input. This is ten digits after +7.  
To make the method return the correct number, use conditions in the body:
* If a non-integer is passed, a `ValueError` exception is raised with the text 'Необходимо ввести цифры';
* If the argument has more than 10 characters, a `ValueError` exception is raised with the text 'Необходимо ввести 10 цифр после "+7"';

In all other cases, the method returns the full phone number.

## 9. Additional task.
Write a static method `get_date_and_time`. It returns the date and time of purchase in the following format: ['часы: 13', 'минуты: 31', 'день: 10', 'месяц: 7', 'год: 2023'].  
The method should contain:
* empty list `date_and_time`,
* variable `now`,
* list of lists `date`,
* a `for` loop.

Initialize the now variable with the current date: `datetime.datetime.now()`.  
Save five lists in `date`. Two values in each:
* Name of the time interval. For example, 'часы'.
* A lambda function with argument x. It gets the value of the time interval: x.<time_interval>. For example, x.hour.

Use the loop to add data from the nested lists to `date_and_time` in string format. For example, 'часы: 13'. To get the current time, pass the now variable to the lambda functions in the loop as a parameter.  
The method returns the `date_and_time` list.
