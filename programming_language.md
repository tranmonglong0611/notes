=Hashtable vs HashMap=
    * Hashtable is synchronized, whereas HashMap is not. 
        This makes HashMap better for non-threaded applications, as unsynchronized Objects typically perform better than synchronized ones.
    * Hashtable does not allow null keys or values. HashMap allows one null key and any number of null values

=OOP=
    * Inheritance
    A child will inherit the properties and the methods from a parents

    * Encapsulation
    process of wrapping code and data together into a single unit
    We can create a fully encapsulated class in Java by making all the data members of the class private. 
    Now we can use setter and getter methods to set and get the data in it

    * polymorphims 
    is a concept by which we can perform a single action in different ways
    to allow an entity such as a variable, a function, or an object to have more than one form
    For example, cat and dog derevied from animals and override the bark method

=Java servlet=
A servlet at its very core is a java class; which can handle HTTP requests. 
Typically the internal nitty-gritty of reading a HTTP request and response over the wire is taken care of by the containers like Tomcat. 
This is done so that as a server side developer you can focus on what to do with the HTTP request and responses 
and not bother about dealing with code that deals with networking etc. 
The container will take care of things like wrapping the whole thing in a HTTP response object and send it over to the client (say a browser).

=Enum=
    they are classes that export one instance for each enumeration constant via a public static final field
    public enum Apple  { FUJI, PIPPIN, GRANNY_SMITH }
    public enum Orange { NAVEL, TEMPLE, BLOOD }


=Synchronous=
    * Synchronous: lock on object. Every block code need synchrounous will need to wait a lock to execute that code block
    atomic:
    * Volatile: just visibility. Should use when one thread write and others read

=Cookie vs Session=
    * Cookie is saved in the web browser to save user info
    * Session is also used to save user info but saved in the server. Can use JSESSIONID,
    save it at cookie to get back the session we need
