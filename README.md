# UML Spring Code Generator

The goal of this project is to generate Java code in the architecture used by Spring Boot projects, for generic domains, based on a class diagram of domains created in Astah.

## Dependencies

1. Git
2. Astah
3. AnyCode

## Usage

First, install the [Anycode plugin for Astah](http://astah.net/features/anycode-plugin);
Create your class diagram following the desires of your heart (or your project);

Select the template path, and then the path where the generated code will be stored (usually ```./result```).
Click on 'Generate' and it's done :D

### Annotations

You can annotate your Astah classes with:
* ```entity```
* ```interface```
* ```final```
* Any other Astah annotation (but we just create custom code for those two)

Our templates create _automagically_ a lot of boilerplate code, based on those annotated classes:
* When annotating with ```nothing at all```
  * Common, boring domain classes. Boo.
* When using ```interface```
  * Common interfaces. A _little_ less poopy.
* With ```final```
  * Incredible, non-extend-able-esque, Java ```final``` classes. What were you expecting?
* If you annotate your class with ```entity```, the magic happens:
  * Awesome [Spring](https://spring.io/)-esque Rrepository **and** Controller classes are created, [JPA](https://wikipedia.org/wiki/Java_Persistence_API) annotated domain **and** Service classes.

## Limitations

As with any other internally used plugin, there are no intentions of making these Anycode templates fully abstract and reusable, there will always exist some limitations that we consider to be acceptable. 
That said, there are some requirements that need to be met so this project works just fine:
* All classes that you expect to be "rendered" need to be, and that's **very** important, **inside** a package ob Astah;
* [Associations](http://www.uml-diagrams.org/association.html) **must** be named and have a cardinality defined.




>
> It doesn't matter how mush you try, you alone can't change the world. 
> But that is the beautiful side os the world.
> -- L
>