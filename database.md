#clusterIndex vs nonClusterIndex: 
    * clusterIndex: the row in the table is ordered in the disk same as the way it is ordered in the index data structure. Can have only 1 clusterIndex
     
    * nonClusterIndex: the row in the table is no need ordered in the disk like 
     in the index => can have many nonClusteredIndex

=Key=
    * primaryKey: is 1/many column in a table which must contain a unique value 
     which can be used to uniquely identify a row of table. There are only one 
     primaryKey in table and the values can not be null
     
    * foreignKey: foreignKey of one table will point to primaryKey of another table. It means all the values in foreignKey columns need to be appear in 
        primaryKey colunns of another table
        
    * uniqueKey: is 1/many of a column that uniquely indentify a row of table

=Transaction=
    is a unit of work that will be treat as "a whole". That means all of it will be done or nothing happen.
    
=How to handle race condition=
    * Refractor our sql to just update the table. No read-modify-write cycle
    * Use SERIALIZABLE transactions
    * Optimistic locking. Usually implemented in application level. When you take note
    of the version number of record. And when you update the record you see that version number
    is changed ?. If changed, so roll back
    * Pessimistic locking is when you lock the record until you finished the transaction 
      (commit or roleback). Not good if you usually read and just update sometime
      
=ACID=
    * Atomicity: the entire transaction take places. Or nothing happen
    * Consistency: the database still need to be correct after transaction. A give money to B => sum(A + B) remain
    * Isolation: there will be only one transaction accessing a resource at 1 time
        - Dirty read: Transaction1 read the record that has not been committed
        - Non repeatable read: Transaction1 read the record but T2 change value of record. So T1 will 
          got different data if reread record
        - Phantom read: T1 get some record after search. T2 add some new rows. So T1 will 
          got different record if search again
          
    * Durability: the updates and modifications to the database are stored in and written 
    to disk and they persist even if a system failure occurs

=Isolation level=
    * Read uncommitted: read the uncommited record made by other transaction
    * Read commited: any data read is commited at the moment it is read
    * Repeatable read: if data is read many time in a transaction. Row will not be changed. But maybe have new rows
    * Serializable: all row is the same and not be changed

=SQL vs NoSql=
    [[SQL]]:
    * Complex queries and reports
    * High transaction application
    * Need to ensure ACID compliance
    * You dont anticipate a lot of changes or growth
    [[NoSQL]]
    * Many datas with a lot of different types
    * Constantly add new features, data types ...
    * Data consistency is not your top goal. For example, with social media platforms, 
    it isn’t important if everyone sees your new post at the exact same time, which means data consistency is not a priority.
