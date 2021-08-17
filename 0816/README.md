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
| 01608-001 |01608 | Database Basics | 758573060 |
| 01608-002 |01608 | Database Basics | 758573060 |
| 01608-003 |01608 | Database Basics | 758573060 |
| 00816-001 | 00816 | Learn Javascript | 308056296 |
| 07085-001 | 07085  | HTML and CSS  | 552924853 |
| 07085-002 | 07085 | HTML and CSS  | 552924853 |

**************************************

### Many to Many
I only put the information on Author and Book, I'll add information on the Catalog ID and ISBN if needed

#### Card Catalog
| Catalog  ID  |  Title   | Author | ISBN | 
|------|----------------|--------|--------|
| 01608 | Database Basics | Juan dela Cruz | 758573060 |
| 00816 | Learn Javascript | Pedro Penduko | 308056296 |
| 00816 | Learn Javascript | Nene Penduko | 308056296 |
| 07085 | HTML and CSS  | Piolo Pascual | 552924853 | 


#### Author Details
| Author ID  |  First Name   | Last Name | Date of Birth | Country of Origin
|------|----------------|--------|--------| ------|
| 00001 | Juan | dela Cruz | July 20 1958 | Australia |
| 00618 | Pedro | Penduko | December 25 1978 | Philippines |
| 00186 | Nene | Penduko | January 01 1972 | USA |
| 00106 | Piolo | Pascual | March 01 1972 | Netherlands |


#### Book Details
| Title |  Publisher  | Yr Published | ISBN | 
|------|----------------|--------|--------| 
| Database Basics  | SM Publishing | 2000| 758573060  | 
| Learn Javascript | Megaworld | 1999 | 308056296 |
| HTML and CSS | Ayala | 2010 | 552924853|


#### Catalog ID
Catalog ID |  Title   | Author ID | ISBN | 
|------|------|----------------|--------|
|01608| Database Basics | 00001 | 758573060 |
|00816| Learn Javascript | 00618 | 308056296 |
|00816| Learn Javascript | 00186 | 308056296 |
|07085| HTML and CSS | 07085 |  552924853 |



