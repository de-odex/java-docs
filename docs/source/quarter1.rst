First Quarter
=============

Welcome to Java Docs!


Hello World
-----------
This is a Hello World program coded in java, with the filename "java.java"

.. code-block:: java

    public class java {
        public static void main(String[] args) {
            System.out.println("Hello World");
        }
    }

Some explanations:
 - ``public``, ``static``, ``class``, and ``void`` are called *keywords*

----

Types of keywords:
 - the visibility/access keywords: defines which applications can view the class
    ``public``
        Means literally anything in the java universe can access the class/method
    ``private``
        Means only the class it is in can access it, no matter what; ex. with a program like this::

            public class MainProgram {
                public static class aPublicClass {
                    private static void privFunction(){
                        System.out.println("I can only be printed within this class");
                    }
                }
            }

        You cannot do this::

            import MainProgram.aPublicClass
            public class MainProgram2 {
                public void main(String[] args) {
                    aPublicClass.privFunction();
                }
            }

        But you can do this::

            public class MainProgram {
                public static class aPublicClass {

                    public aPublicClass(){

                    } // this is the "constructor", will be explained soon

                    private void privFunction(){
                        System.out.println("I can only be printed within this class");
                    }

                    public static void runPrivFunction(){
                        aPublicClass apc = new Main.aPublicClass();
                        apc.privFunction();
                    }
                }

                public static void main(String[] args){
                    aPublicClass.runPrivFunction();
                }
            }

        This basically means you're making a

    ``protected``
        Means only the class it is in can access it, though if you make an object of the class you may access it. ex.::

            public class MainProgram {
                public class aPublicClass {
                    private static void privFunction(){
                        System.out.println("I can only be printed within this class");
                    }
                }
            }