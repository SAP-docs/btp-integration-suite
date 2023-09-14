<!-- loio062f7a7e5c374e67b568dddc7b7844a9 -->

# Using Script API Methods in Groovy Scripts



<a name="loio062f7a7e5c374e67b568dddc7b7844a9__prereq_rld_d31_4bb"/>

## Prerequisites

-   You have installed Groovy plugins for Eclipse.



## Context

If you are creating a script based on the *Message* class from SAP, you can use a jar file that contains the definition of the *Message* class in your script project to make your life easier. By using this jar file, Eclipse provides content assist while writing scripts for the *Message* class. This enables you to complete the script easily.

Here's how you can import this jar into your script project:



## Procedure

1.  Download the JAR from the *Using Script API* section of the [Cloud Integration Tools Page](https://tools.hana.ondemand.com/#cloudintegration).

2.  Create a new *Groovy Project*.

3.  In the *Build Settings*, choose *Add External JARs* to add the downloaded JAR file to your groovy project.

4.  When you create a new groovy class, reference the groovy script project where you have added the JAR.




<a name="loio062f7a7e5c374e67b568dddc7b7844a9__result_cqs_52b_4bb"/>

## Results

When you are creating the script, Eclipse automatically suggests options when you are inserting methods from *Message* class.

