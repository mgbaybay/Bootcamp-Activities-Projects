# 0816 Database Relationship

### One to Many

#### Catalog Entry Example
| Catalog ID |    Title   | ISBN |  
|------|----------------|--------|
| 01608 | Database Basics | 758573060 |
| 00816 | Learn Javascript | 308056296 | 
| 07085 | HTML and CSS  | 552924853 |

#### Book on Shelf Example
| Book ID |  Catalog ID  |  Title   | ISBN | 
|------|----------------|--------|--------|
| 01 |01608 | Database Basics | 758573060 |
| 02 |01608 | Database Basics | 758573060 |
| 03 |01608 | Database Basics | 758573060 |
| 01 | 00816 | Learn Javascript | 308056296 |
| 01 | 07085  | HTML and CSS  | 552924853 |
| 02 | 07085 | HTML and CSS  | 552924853 |

### Many to Many
I only put the information on Author and Book, I'll add information on the Catalog ID and ISBN if needed
