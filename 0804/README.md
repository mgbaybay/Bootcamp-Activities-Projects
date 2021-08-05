# 0804 JS Library
*For this activity, two different ways of constructing an object were used.

FIRST METHOD - OBJECT LITERAL
1. An object named _bookDetails_ by using **object literal** was constructed.
2. Inside _bookDetails_, all properties of each books were written.
3. Sorting and separation were done later.

SECOND METHOD - OBJECT CONSTRUCTOR
1. For this method, a function named _bookDetails_ by using **object constructor** was constructed.
2. bookDetails have the following arguments _(libraryid, bookName, bookAuthor, yearPublished, isRead)_.
3. Argument values were defined inside bookDetails by using "this" keyword.
4. To create new objects, "let" and "new" keywords were used.
5. An array named _bookShelf_ was created to store all books for easier sorting/separation later.

******************************************

SORTING BOOKS
1. To sort the books by their name, the built-in **sort()** function in JS was used.
2. The sort function takes two items named _book1_ and _book2_ for comparison to arrange them in ascending order.
3. The function returns -1 if the items being compared don't need to be sorted.
4. Otherwise, the function returns 1 which means that the items need to be sorted.
5. If the function was successfully executed, it returns 0.

SEPARATING READ AND UNREAD BOOKS
1. An array _book_is_read_ stores books that have been read.
2. An array _book_is_not_read_ stores books that have not been read.
3. IF ELSE was used to iterate each books and check if they have been read or not, then stores each books according to their respective containers. 
