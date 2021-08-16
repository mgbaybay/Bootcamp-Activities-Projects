# 0816 Database Relationship

### One to Many

#### Catalog Entry Example
| Catalog ID |    Title   | ISBN |  
|------|----------------|--------|
| 01608 | Database Basics | 758573060 |
| 00816 | Learn Javascript | 308056296 | 
| 07085 | HTML and CSS  | 552924853 |

#### Book on Shelf Example
| Book ID |  Catalog ID  |
|------|----------------|
| 01 |01608 |
| 02 |01608 |
| 03 |01608 |
| 01 | 00816 | 
| 01 | 070807085  |
| 02 | 070807085  |

### Many to Many
I only put the information on Author and Book, I'll add information on the Catalog ID and ISBN if needed
