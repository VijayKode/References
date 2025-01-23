what is dirty read and write?

Dirty read and dirty write are concepts related to database transactions and concurrency control. Here's an explanation:

Dirty Read
A dirty read occurs when a transaction reads data that has been modified by another transaction but has not yet been committed. If the modifying transaction rolls back, the data read by the first transaction becomes invalid or "dirty."

Example of Dirty Read:

Transaction A updates a row in the database but does not commit the change.
Transaction B reads the updated value from the row.
If Transaction A rolls back the update, the data read by Transaction B is no longer valid.

Problem:
Dirty reads can cause inconsistencies because one transaction is acting on uncommitted changes made by another transaction.

Dirty Write
A dirty write occurs when one transaction overwrites data that has been modified by another transaction but has not yet been committed. This can lead to data corruption if one of the transactions rolls back.

Example of Dirty Write:
Transaction A updates a row in the database but does not commit the change.
Transaction B writes to the same row without considering Transaction A's changes.
If either transaction rolls back, the resulting data may be inconsistent.
