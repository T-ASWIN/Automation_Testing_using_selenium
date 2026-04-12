
In Java, StringBuffer is a mutable class used to create and modify strings that can change, especially in multithreaded environments. 
Shape 

StringBuffer is a mutable sequence of characters that is threadsafe (synchronized). 

StringBuffer sb = new StringBuffer("Hello");
sb.append(" World");

sb.insert(5, ",");

sb.delete(5, 11);

System.out.println(sb);   // Hello World


