# 0805 Shopping Cart
*For this activity, three different ways of computing the shopping cart total were used.

FIRST METHOD - BY USING CLASS ONLY
1. A class named _Product_ with constructor _name_ and _price_ was created.
2. Argument values were defined inside _Product_ by using "this" keyword.
3. Another class named _ShoppingCart_ with constructor _cartItems_ (an array) and _totalPrice_ was created.
4. Inside _ShoppingCart_, a function named _addtoCart_, with parameter _product_ was added
5. 
3. To create new objects, "let" and "new" keywords were used.
2. Inside _bookDetails_, all properties of each books were written.
3. Sorting and separation were done later.

SECOND METHOD - BY USING FUNCTION
1. For this method, a function named _bookDetails_ by using **object constructor** was constructed.
2. bookDetails have the following arguments _(libraryid, bookName, bookAuthor, yearPublished, isRead)_.
3. Argument values were defined inside bookDetails by using "this" keyword.
4. To create new objects, "let" and "new" keywords were used.
5. An array named _bookShelf_ was created to store all books for easier sorting/separation later.

THIRD METHOD - BY FOR LOOP
1. FOR LOOP was used to get the total price of the products
2. Each product was stored in an array _item_list_
3. FOR LOOP iterates on each 

******************************************

GETTING THE TOTAL PRICE
1. To sort the books by their name, the built-in **sort()** function in JS was used.
2. The sort function takes two items named _book1_ and _book2_ for comparison to arrange them in ascending order.
3. The function returns -1 if the items being compared don't need to be sorted.
4. Otherwise, the function returns 1 if the items need to be sorted.
5. If the function was successfully executed, it returns 0.

PRINTING THE ITEM LIST
1. The array _productList_ stores and prints the list of products
