# ER Diagram

## ENTITY

### ITEM

ID (PRIMARY KEY)

NAME

PAGE\_VISIT\_COUNTER

DESCRIPTION

CONDITION

PRICE

TYPE

EXPIRY_DATE (
YEAR
MONTH
DAY
)

PICTURE

### COMMENT

ID (PRIMARY KEY)

CONTENT

POST\_DATE (
YEAR
MONTH
DAY
)

### CLIENT (overlap: SELLER, BUYER)

ID (PRIMARY KEY)

PASSWORD

PASSWORD\_QUESTION

ANSWER\_OF\_PASSWORD\_QUESTION

ADDRESS

ACCOUNT\_STATUS

PHONE\_NUMBER

DATE\_OF\_REGISTRATION (
YEAR
MONTH
DAY
)

USERNAME

### UCALGARY_MEMBER

UCID (PRIMARY KEY)

CAMPUS\_EMAIL\_ADDRESS

NAME (
FIRST\_NAME
MIDDLE\_INITIAL
LAST\_NAME
)

DATE\_OF\_BIRTH (
YEAR
MONTH
DAY
)

GENDER

BALANCE

### ANNOUNCEMENT

ID (PRIMARY KEY)

POST\_DATE (
YEAR
MONTH
DAY
)

TITLE

CONTENT

### ADMINISTRATOR

ID (PRIMARY KEY)

PASSWORD

PASSWORD\_QUESTION

ANSWER\_OF\_PASSWORD\_QUESTION

ADDRESS

USERNAME

PHONE_NUMBER

EMAIL_ADDRESS

DATE\_OF\_REGISTRATION (
YEAR
MONTH
DAY
)

DATE\_OF\_BIRTH (
YEAR
MONTH
DAY
)

NAME (
FIRST\_NAME
MIDDLE\_INITIAL
LAST\_NAME
)

### ORDER

ID (PRIMARY KEY)

TOTAL\_PRICE

STATUS

ADDRESS\_OF\_RECEIVER

NAME\_OF\_RECEIVER (
FIRST\_NAME
MIDDLE\_INITIAL
LAST\_NAME
)

SHIPPING\_METHOD

DATE\_OF\_ORDER (
YEAR
MONTH
DAY
)

### IDEA_LIST (WEAK, no PRIMARY)

LIST_NUMBER (partial)

NAME

KEYWORD (multivalue)

DESCRIPTION

## RELATION

### POSTS

A CLIENT POSTS COMMENTS

### CONTAINS (1:N) (paritial/fully)

AN ITEM CONTAINS COMMENTS

### IS_A (1:1) (full/partial)

A CLIENT IS A UCALGARY_MEMBER

### HOLDS (1:N) (partial/full)

AN ITEM HOLDS ORDERS

### UNPUBLISHES

AN ADMINISTRATOR UNPUBLISHES ITEMS

### MANAGES

AN ADMINISTRATOR MANAGES ORDERS/ANNOUNCEMENTS/COMMENTS/CLIENTS/UCALGARY_MEMBER

### MANAGES

A SELLER MANAGES ORDERS

### PUBLISHES

A SELLER PUBLISHES ITEMS

### UNPUBLISHES

A SELLER UNPUBLISHES ITEMS

### MAKES

A BUYER MAKES ORDERS

### PURCHASES

A BUYER PURCHASES ITEMS

### CREATES (1:N) (partial/full)

A CLIENT CREATES IDEA LISTS

#####


1. This is a revised edition of the work submitted on Oct 11, 2019.

2. The reason why we created UCALGARY_MEMBER as an entity type is because it helps us validate all guests during account registration and makes sure they are members of UCalgary. In real world, such policy may be implemented by using a set of APIs provided by UCalgary.

3. The entity type 'RANK' is removed since we plan to rank by attributes of 'ITEM'.

4. The entity type 'TYPE_OF_GOODS' is removed since we made 'TYPE' as an attribute of 'ITEM'.

5. We created a new weak entity type 'IDEA_LIST'.

6. In order to keep conformity, we change characters to uppercase. Meanwhile, we rename some relationships and entity types to eliminate ambiguity.


