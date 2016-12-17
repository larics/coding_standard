#C++ Programming Style Guidelines

##Table of Contents

- [1 Introduction](#introduction)
  * [1.1 Layout of the Recommendations](#introductionLayoutOfTheRecommendations)
  * [1.2 Recommendation importance](#introductionRecommendationImportance)
- [2 General Recommendations](#GeneralRecommendations)
- [3 Naming Conventions](#NamingConventions)
  * [3.1 General Naming Conventions](#NamingConventionsGeneralNamingConventions)
  * [3.2 Specific Naming Conventions](#NamingConventionsSpecificNamingConventions)
- [4 Files](#Files)
  * [4.1 Source Files](#FilesSourceFiles)
  * [4.2 Include Files and Include Statements](#FilesIncludeFilesAndIncludeStatements)
- [5 Statements](#Statements)
  * [5.1 Types](#StatementsTypes)
  * [5.2 Variables](#StatementsVariables)
  * [5.3 Loops](#StatementsLoops)
  * [5.4 Conditionals](#StatementsConditionals)
  * [5.5 Miscellaneous](#StatementsMiscellaneous)
- [6 Layout and Comments](#LayoutAndComments)
  * [6.1 Layout](#LayoutAndCommentsLayout)
- [7 References](#references)


<!-- Table for the layout of the recommendations
|<span style="background-color:lightblue">  </span>|
|:------------- |
|<pre> <br> </pre>|
||
<br>
-->
## <a name="introduction"></a> 1 Introduction
This document lists C++ coding recommendations common in the C++ development community.

The recommendations are based on established standards collected from a number of sources, individual experience, local requirements/needs, as well as suggestions given in [1](#reference1) - [4](reference4).

There are several reasons for introducing a new guideline rather than just referring to the ones above. The main reason is that these guides are far too general in their scope and that more specific rules (especially naming rules) need to be established. Also, the present guide has an annotated form that makes it far easier to use during project code reviews than most other existing guidelines. In addition, programming recommendations generally tend to mix style issues with language technical issues in a somewhat confusing manner. The present document does not contain any C++ technical recommendations at all, but focuses mainly on programming style. For guidelines on C++ programming style refer to the [C++ Programming Practice Guidelines](http://geosoft.no/development/cpppractice.html).

While a given development environment (IDE) can improve the readability of code by access visibility, color coding, automatic formatting and so on, the programmer should never rely on such features. Source code should always be considered larger than the IDE it is developed within and should be written in a way that maximise its readability independent of any IDE.

### <a name="introductionLayoutOfTheRecommendations"></a> 1.1 Layout of the Recommendations
The recommendations are grouped by topic and each recommendation is numbered to make it easier to refer to during reviews.

Layout of the recommendations is as follows:

|<span style="background-color:lightblue"> n. Guideline short description. </span>|
|:------------- |
|<pre> Example if applicable <br> Code... </pre>|
|Motivation, background and additional information.| 

The motivation section is important. Coding standards and guidelines tend to start "religious wars", and it is important to state the background for the recommendation.

### <a name="introductionRecommendationImportance"></a> 1.2 Recommendation importance
In the guideline sections the terms *must*, *should* and *can* have special meaning. A *must* requirement must be followed, a *should* is a strong recommendation, and a *can* is a general guideline.

## <a name="GeneralRecommendations"></a> 2 General Recommendations
|<span style="background-color:lightblue"> 1. Any violation to the guide is allowed if it enhances readability. </span>|
|:------------- |
||
|The main goal of the recommendation is to improve readability and thereby the understanding and the maintainability and general quality of the code. It is impossible to cover all the specific cases in a general guide and the programmer should be flexible.
|

|<span style="background-color:lightblue">2. The rules can be violated if there are strong personal objections against them. </span>|
|:------------- |
||
|The attempt is to make a guideline, not to force a particular coding style onto individuals. Experienced programmers normally want to adopt a style like this anyway, but having one, and at least requiring everyone to get familiar with it, usually makes people start *thinking* about programming style and evaluate their own habits in this area. <br> On the other hand, new and inexperienced programmers normally use a style guide as a convenience of getting into the programming jargon more easily.| 

## <a name="NamingConventions"></a> 3 Naming Conventions
### <a name="NamingConventionsGeneralNamingConventions"></a> 3.1 General Naming Conventions
|<span style="background-color:lightblue"> 3. Names representing types must be in mixed case starting with upper case. </span>|
|:------------- |
|<pre> Line, SavingsAccount </pre>|
|Common practice in the C++ development community.| 
<br>

|<span style="background-color:lightblue"> 4. Variable names must be in mixed case starting with lower case. </span>|
|:------------- |
|<pre> line, savingsAccount </pre>|
|Common practice in the C++ development community. Makes variables easy to distinguish from types, and effectively resolves potential naming collision as in the declaration Line line;|
<br>

|<span style="background-color:lightblue"> 5. Named constants (including enumeration values) must be all uppercase using underscore to separate words. </span>|
|:------------- |
|<pre> MAX_ITERATIONS, COLOR_RED, PI </pre>|
|Common practice in the C++ development community. In general, the use of such constants should be minimized. In many cases implementing the value as a method is a better choice: <br> <pre>int getMaxIterations() // NOT: MAX_ITERATIONS = 25 <br>{ <br>  return 25; <br>} </pre> This form is both easier to read, and it ensures a unified interface towards class values.| 
<br>

|<span style="background-color:lightblue"> 6. Names representing methods or functions must be verbs and written in mixed case starting with lower case. </span>|
|:------------- |
|<pre> getName(), computeTotalWidth() </pre>|
|Common practice in the C++ development community. This is identical to variable names, but functions in C++ are already distingushable from variables by their specific form.| 
<br>

|<span style="background-color:lightblue"> 7. Names representing namespaces should be all lowercase. </span>|
|:------------- |
|<pre> model::analyzer, io::iomanager, common::`math`::geometry </pre>|
|Common practice in the C++ development community.| 
<br>

|<span style="background-color:lightblue"> 8. Names representing template types should be a single uppercase letter. </span>|
|:------------- |
|<pre> template`<class T>` ... <br> template`<class C, class D>` ... </pre>|
|Common practice in the C++ development community. This makes template names stand out relative to all other names used.| 
<br>

|<span style="background-color:lightblue"> 9. Abbreviations and acronyms must not be uppercase when used as name [[4](#reference4)]. </span>|
|:------------- |
|<pre> exportHtmlSource(); // NOT: exportHTMLSource(); <br> openDvdPlayer();    // NOT: openDVDPlayer(); </pre>|
|Using all uppercase for the base name will give conflicts with the naming conventions given above. A variable of this type whould have to be named dVD, hTML etc. which obviously is not very readable. Another problem is illustrated in the examples above; When the name is connected to another, the readbility is seriously reduced; the word following the abbreviation does not stand out as it should.| 
<br>


|<span style="background-color:lightblue"> 10. Global variables should always be referred to using the :: operator. </span>|
|:------------- |
|<pre> ::mainWindow.open(), ::applicationContext.getName() </pre>|
|In general, the use of global variables should be avoided. Consider using singleton objects instead.| 
<br>

|<span style="background-color:lightblue">  11. Private class variables should have underscore suffix. </span>|
|:------------- |
|<pre> class SomeClass { <br>   private: <br>     int length_; <br> } </pre>|
|Apart from its name and its type, the *scope* of a variable is its most important feature. Indicating class scope by using underscore makes it easy to distinguish class variables from local scratch variables. This is important because class variables are considered to have higher significance than method variables, and should be treated with special care by the programmer. <br> A side effect of the underscore naming convention is that it nicely resolves the problem of finding reasonable variable names for setter methods and constructors: <br> <pre>void setDepth (int depth) <br>{ <br>  depth_ = depth; <br>} </pre> An issue is whether the underscore should be added as a prefix or as a suffix. Both practices are commonly used, but the latter is recommended because it seem to best preserve the readability of the name. <br> <br> It should be noted that scope identification in variables has been a controversial issue for quite some time. It seems, though, that this practice now is gaining acceptance and that it is becoming more and more common as a convention in the professional development community.| 
<br>


|<span style="background-color:lightblue"> 12. Generic variables should have the same name as their type. </span>|
|:------------- |
|<pre>void setTopic(Topic* topic) // NOT: void setTopic(Topic* value) <br>                           // NOT: void setTopic(Topic* aTopic) <br>                           // NOT: void setTopic(Topic* t) <br><br>void connect(Database* database) // NOT: void connect(Database* db) <br>                                // NOT: void connect (Database* oracleDB) </pre>|
|Reduce complexity by reducing the number of terms and names used. Also makes it easy to deduce the type given a variable name only. <br> <br>If for some reason this convention doesn't seem to fit it is a strong indication that the type name is badly chosen. <br> <br>Non-generic variables have a role. These variables can often be named by combining role and type: <pre>Point  startingPoint, centerPoint; <br>Name   loginName;</pre>| 
<br>

|<span style="background-color:lightblue"> 13. All names should be written in English. </span>|
|:------------- |
|<pre> fileName;   // NOT: imeDatoteke </pre>|
|English is the preferred language for international development.| 
<br>

|<span style="background-color:lightblue"> 14. Variables with a large scope should have long names, variables with a small scope can have short names [[1](#reference1)]. </span>|
|:------------- |
||
|Scratch variables used for temporary storage or indices are best kept short. A programmer reading such variables should be able to assume that its value is not used outside of a few lines of code. Common scratch variables for integers are *i*, *j*, *k*, *m*, *n* and for characters *c* and *d*.| 
<br>

|<span style="background-color:lightblue"> 15. The name of the object is implicit, and should be avoided in a method name. </span>|
|:------------- |
|<pre> line.getLength();   // NOT: line.getLineLength(); </pre>|
|The latter seems natural in the class declaration, but proves superfluous in use, as shown in the example.| 
<br>

### <a name="NamingConventionsSpecificNamingConventions"></a> 3.2 Specific Naming Conventions

|<span style="background-color:lightblue"> 17. The terms *get/set* must be used where an attribute is accessed directly. </span>|
|:------------- |
|<pre>employee.getName(); <br>employee.setName(name); <br><br>matrix.getElement(2, 4); <br>matrix.setElement(2, 4, value);</pre>|
|Common practice in the C++ development community. In Java this convention has become more or less standard.| 

|<span style="background-color:lightblue"> 18. The term *compute* can be used in methods where something is computed. </span>|
|:------------- |
|<pre>valueSet->computeAverage(); <br>matrix->computeInverse(); </pre>|
|Give the reader the immediate clue that this is a potentially time-consuming operation, and if used repeatedly, he might consider caching the result. Consistent use of the term enhances readability.|
<br>

|<span style="background-color:lightblue"> 19. The term *find* can be used in methods where something is looked up. </span>|
|:------------- |
|<pre>vertex.findNearestVertex(); <br>matrix.findMinElement(); </pre>|
|Give the reader the immediate clue that this is a simple look up method with a minimum of computations involved. Consistent use of the term enhances readability.|
<br>

|<span style="background-color:lightblue"> 20. The term *initialize* can be used where an object or a concept is established. </span>|
|:------------- |
|<pre>printer.initializeFontSet();</pre>|
|The american *initialize* should be preferred over the English *initialise*. Abbreviation *init* should be avoided.|
<br>

|<span style="background-color:lightblue"> 21. Variables representing GUI components should be suffixed by the component type name. </span>|
|:------------- |
|<pre>mainWindow, propertiesDialog, widthScale, loginText, <br>leftScrollbar, mainForm, fileMenu, minLabel, exitButton, yesToggle etc. </pre>|
|Enhances readability since the name gives the user an immediate clue of the type of the variable and thereby the objects resources.|
<br>

|<span style="background-color:lightblue"> 22. Plural form should be used on names representing a collection of objects. </span>|
|:------------- |
|<pre>vector`<Point>`  points; <br>int            values[]; </pre>|
|Enhances readability since the name gives the user an immediate clue of the type of the variable and the operations that can be performed on its elements.|
<br>

|<span style="background-color:lightblue"> 23. The prefix *n* should be used for variables representing a number of objects. </span>|
|:------------- |
|<pre> nPoints, nLines </pre>|
|The notation is taken from mathematics where it is an established convention for indicating a number of objects.|
<br>

|<span style="background-color:lightblue"> 24.The suffix *No* should be used for variables representing an entity number. </span>|
|:------------- |
|<pre> tableNo, employeeNo </pre>|
|The notation is taken from mathematics where it is an established convention for indicating an entity number. <br> <br>An elegant alternative is to prefix such variables with an i: `iTable, iEmployee`. This effectively makes them *named iterators*.|
<br>

|<span style="background-color:lightblue"> 25. Iterator variables should be called *i*, *j*, *k* etc. </span>|
|:------------- |
|<pre>for (int i = 0; i < nTables); i++) { <br>  : <br>} <br> <br>for (vector<MyClass>::iterator i = list.begin(); i != list.end(); i++) { <br>  Element element = *i; <br>  ... <br>} </pre>|
|The notation is taken from mathematics where it is an established convention for indicating iterators. <br> <br>Variables named *j*, *k* etc. should be used for nested loops only.|
<br>

|<span style="background-color:lightblue"> 26. The prefix *is* should be used for boolean variables and methods. </span>|
|:------------- |
|<pre> isSet, isVisible, isFinished, isFound, isOpen </pre>|
|Common practice in the C++ development community and partially enforced in Java. <br> <br> Using the *is* prefix solves a common problem of choosing bad boolean names like status or `flag. isStatus` or `isFlag` simply doesn't fit, and the programmer is forced to choose more meaningful names. <br> <br> There are a few alternatives to the *is* prefix that fit better in some situations. These are the *has*, *can* and *should* prefixes: <br> `bool hasLicense();` <br>`bool canEvaluate();` <br>`bool shouldSort();`|
<br>

|<span style="background-color:lightblue"> 27. Complement names must be used for complement operations [[1](#reference1)]. </span>|
|:------------- |
|<pre>get/set, add/remove, create/destroy, start/stop, insert/delete, <br>increment/decrement, old/new, begin/end, first/last, up/down, min/max, <br>next/previous, old/new, open/close, show/hide, suspend/resume, etc. </pre>|
|Reduce complexity by symmetry.|
<br>

|<span style="background-color:lightblue"> 28. Abbreviations in names should be avoided. </span>|
|:------------- |
|<pre> computeAverage();   // NOT: compAvg(); </pre>|
|There are two types of words to consider. First are the common words listed in a language dictionary. These must never be abbreviated. **Never write**: <br> <pre>cmd   instead of   command <br>cp    instead of   copy <br>pt    instead of   point <br>comp  instead of   compute <br>init  instead of   initialize <br>etc. </pre> <br> Then there are domain specific phrases that are more naturally known through their abbreviations/acronym. These phrases should be kept abbreviated. **Never write**: <pre>HypertextMarkupLanguage  instead of   html <br>CentralProcessingUnit    instead of   cpu <br>PriceEarningRatio        instead of   pe|
<br>

|<span style="background-color:lightblue"> 29. Naming pointers specifically should be avoided. </span>|
|:------------- |
|<pre> Line* line; // NOT: Line* pLine; <br>            // NOT: LIne* linePtr; </pre>|
|Many variables in a C/C++ environment are pointers, so a convention like this is almost impossible to follow. Also objects in C++ are often oblique types where the specific implementation should be ignored by the programmer. Only when the actual type of an object is of special significance, the name should emphasize the type.|
<br>

|<span style="background-color:lightblue"> 30. Negated boolean variable names must be avoided. </span>|
|:------------- |
|<pre>bool isError; // NOT: isNoError <br>bool isFound; // NOT: isNotFound </pre>|
|The problem arises when such a name is used in conjunction with the logical negation operator as this results in a double negative. It is not immediately apparent what `!isNotFound` means.|
<br>

|<span style="background-color:lightblue"> 31. Enumeration constants can be prefixed by a common type name. </span>|
|:------------- |
|<pre>enum Color { <br>  COLOR_RED, <br>  COLOR_GREEN, <br>  COLOR_BLUE <br>}; </pre>|
|This gives additional information of where the declaration can be found, which constants belongs together, and what concept the constants represent. <br> <br> An alternative approach is to always refer to the constants through their common type: `Color::RED`, `Airline::AIR_FRANCE` etc. <br> <br> Note also that the enum name typically should be singular as in `enum Color {...}`. A plural name like `enum Colors {...}` may look fine when declaring the type, but it will look silly in use.|
<br>

|<span style="background-color:lightblue"> 32. Exception classes should be suffixed with *Exception*. </span>|
|:------------- |
|<pre>class AccessException <br>{ <br>  : <br>} </pre>|
|Exception classes are really not part of the main design of the program, and naming them like this makes them stand out relative to the other classes.|
<br>

|<span style="background-color:lightblue"> 33. Functions (methods returning something) should be named after what they return and procedures (*void* methods) after what they do. </span>|
|:------------- |
||
|Increase readability. Makes it clear what the unit should do and especially all the things it is not supposed to do. This again makes it easier to keep the code clean of side effects.|
<br>

## <a name="Files"></a> 4 Files

### <a name="FilesSourceFiles"></a> 4.1 Source Files

|<span style="background-color:lightblue"> 34. C++ header files should have the extension .h (preferred) or .hpp. Source files can have the extension .cpp (recommended), .C, .cc or .c++. </span>|
|:------------- |
|<pre> MyClass.c++, MyClass.h </pre>|
|These are all accepted C++ standards for file extension.|
<br>

|<span style="background-color:lightblue"> 35. A class should be declared in a header file and defined in a source file where the name of the files match the name of the class. </span>|
|:------------- |
|<pre> MyClass.h, MyClass.cpp </pre>|
|Makes it easy to find the associated files of a given class. An obvious exception is template classes that must be both declared and defined inside a .h file.|
<br>

|<span style="background-color:lightblue"> 36. All definitions should reside in source files. </span>|
|:------------- |
|<pre>class MyClass <br>{ <br>public: <br>  int getValue () {return value_;}  // NO! <br>    ... <br> <br>private: <br>  int value_; <br>} </pre>|
|The header files should declare an interface, the source file should implement it. When looking for an implementation, the programmer should always know that it is found in the source file.|
<br>

|<span style="background-color:lightblue"> 37. File content must be kept within 80 columns. </span>|
|:------------- |
||
|80 columns is a common dimension for editors, terminal emulators, printers and debuggers, and files that are shared between several people should keep within these constraints. It improves readability when unintentional line breaks are avoided when passing a file between programmers.|
<br>

|<span style="background-color:lightblue"> 38. Special characters like TAB and page break must be avoided. </span>|
|:------------- |
||
|These characters are bound to cause problem for editors, printers, terminal emulators or debuggers when used in a multi-programmer, multi-platform environment. **Note:** You may still use TAB key, just set your editor to fill it with spaces instead *\t* character.|
<br>

|<span style="background-color:lightblue"> 39. The incompleteness of split lines must be made obvious [[1](#reference1)]. </span>|
|:------------- |
|<pre>totalSum = a + b + c + <br>           d + e; <br> <br>function(param1, param2, <br>         param3); <br> <br>setText ("Long line split" <br>         "into two parts."); <br> <br>for (int tableNo = 0; tableNo < nTables; <br>     tableNo += tableStep) { <br>  ... <br>}</pre>|
|Split lines occurs when a statement exceed the 80 column limit given above. It is difficult to give rigid rules for how lines should be split, but the examples above should give a general hint. <br> <br> In general: <br> <br> <ul><li>Break after a comma</li> <li>Break after an operator.</li> <li>Align the new line with the beginning of the expression on the previous line.</li> </ul>|
<br>

### <a name="FilesIncludeFilesAndIncludeStatements"></a> 4.1  Include Files and Include Statements

|<span style="background-color:lightblue"> 40. Header files must contain an include guard. </span>|
|:------------- |
|<pre>`#`ifndef COM_COMPANY_MODULE_CLASSNAME_H <br>`#`define COM_COMPANY_MODULE_CLASSNAME_H <br>  : <br>`#`endif // COM_COMPANY_MODULE_CLASSNAME_H </pre>|
|The construction is to avoid compilation errors. The name convention resembles the location of the file inside the source tree and prevents naming conflicts.|
<br>

|<span style="background-color:lightblue"> 41. Include statements should be sorted and grouped. Sorted by their hierarchical position in the system with low level files included first. Leave an empty line between groups of include statements. </span>|
|:------------- |
|<pre>`#`include `<fstream>` <br>`#`include `<iomanip>` <br> <br>`#`include `<qt/qbutton.h>` <br>`#`include `<qt/qtextfield.h>` <br> <br>`#`include "com/company/ui/PropertiesDialog.h" <br>`#`include "com/company/ui/MainWindow.h" </pre>|
|In addition to show the reader the individual include files, it also give an immediate clue about the modules that are involved. <br> <br>Include file paths must never be absolute. Compiler directives should instead be used to indicate root directories for includes.|
<br>

|<span style="background-color:lightblue"> 42. Include statements must be located at the top of a file only. </span>|
|:------------- |
||
|Common practice. Avoid unwanted compilation side effects by "hidden" include statements deep into a source file.|
<br>

## <a name="Statements"></a> 5 Statements

### <a name="StatementsTypes"></a> 5.1 Types

|<span style="background-color:lightblue"> 43. Types that are local to one file only can be declared inside that file. </span>|
|:------------- |
||
|Enforces information hiding.|
<br>

|<span style="background-color:lightblue"> 44. The parts of a class must be sorted *public*, *protected* and *private* [[2](#reference2)] [[3](#reference3)]. All sections must be identified explicitly. Not applicable sections should be left out. </span>|
|:------------- |
||
|The ordering is "*most public first*" so people who only wish to use the class can stop reading when they reach the protected/private sections.|
<br>

|<span style="background-color:lightblue"> 45. Type conversions must always be done explicitly. Never rely on implicit type conversion. </span>|
|:------------- |
|<pre> floatValue = static_cast<float>(intValue); // NOT: floatValue = intValue; </pre>|
|By this, the programmer indicates that he is aware of the different types involved and that the mix is intentional.|
<br>

### <a name="StatementsVariables"></a> 5.2 Variables

|<span style="background-color:lightblue"> 46. Variables should be initialized where they are declared. </span>|
|:------------- |
||
|This ensures that variables are valid at any time. Sometimes it is impossible to initialize a variable to a valid value where it is declared: <br><br> `int x, y, z;` <br>`getCenter(&x, &y, &z);` <br> <br> In these cases it should be left uninitialized rather than initialized to some phony value.|
<br>

|<span style="background-color:lightblue"> 47. Variables must never have dual meaning. </span>|
|:------------- |
||
|Enhance readability by ensuring all concepts are represented uniquely. Reduce chance of error by side effects.|
<br>

|<span style="background-color:lightblue"> 48. Use of global variables should be minimized. </span>|
|:------------- |
||
|In C++ there is no reason global variables need to be used at all. The same is true for global functions or file scope (static) variables.|
<br>

|<span style="background-color:lightblue"> 49. Class variables should never be declared public. </span>|
|:------------- |
||
|The concept of C++ information hiding and encapsulation is violated by public variables. Use private variables and access functions instead. One exception to this rule is when the class is essentially a data structure, with no behavior (equivalent to a C *struct*). In this case it is appropriate to make the class' instance variables public [[2](#reference2)]. <br> Note that *structs* are kept in C++ for compatibility with C only, and avoiding them increases the readability of the code by reducing the number of constructs used. Use a class instead.|
<br>

|<span style="background-color:lightblue"> 51. C++ pointers and references should have their reference symbol next to the name rather than to the type. </span>|
|:------------- |
|<pre>float `*`x; // NOT: float`*` x; <br>int &y;  // NOT: int& y;</pre>|
|The pointer-ness or reference-ness of a variable is a property of the type rather than the name. However, it's not convenient to declare more than one pointer per line in this case.|
<br>

|<span style="background-color:lightblue"> 53. Implicit test for 0 should not be used other than for boolean variables and pointers. </span>|
|:------------- |
|<pre>if (nLines != 0)  // NOT: if (nLines) <br>if (value != 0.0) // NOT: if (value)</pre>|
|It is not necessarily defined by the C++ standard that ints and floats 0 are implemented as binary 0. Also, by using an explicit test the statement gives an immediate clue of the type being tested. <br> <br>It is common also to suggest that pointers shouldn't test implicitly for 0 either, i.e. if (line == 0) instead of if (line). The latter is regarded so common in C/C++ however that it can be used.|
<br>

|<span style="background-color:lightblue"> 54. Variables should be declared in the smallest scope possible. </span>|
|:------------- |
||
|Keeping the operations on a variable within a small scope, it is easier to control the effects and side effects of the variable.|
<br>

### <a name="StatementsLoops"></a> 5.3 Loops

|<span style="background-color:lightblue"> 55. Only loop control statements must be included in the *for()* construction. </span>|
|:------------- |
|<pre>sum = 0;                       // NOT: for (i = 0, sum = 0; i < 100; i++) <br> for (i = 0; i < 100; i++)               sum += value[i]; <br>   sum += value[i]; </pre>|
|Increase maintainability and readability. Make a clear distinction of what controls and what is *contained* in the loop.|
<br>

|<span style="background-color:lightblue"> 56. Loop variables should be initialized immediately before the loop. </span>|
|:------------- |
|<pre>isDone = false;           // NOT: bool isDone = false; <br>while (!isDone) {         //      : <br>  :                       //      while (!isDone) { <br>}                         //        : <br>                          //      } </pre>|
||
<br>

|<span style="background-color:lightblue"> 57. *do-while* loops can be avoided. </span>|
|:------------- |
||
|*do-while* loops are less readable than ordinary *while* loops and *for* loops since the conditional is at the bottom of the loop. The reader must scan the entire loop in order to understand the scope of the loop. <br> <br> In addition, *do-while* loops are not needed. Any *do-while* loop can easily be rewritten into a *while* loop or a *for* loop. Reducing the number of constructs used enhance readbility.|
<br>

|<span style="background-color:lightblue"> 58. The use of *break* and *continue* in loops should be avoided. </span>|
|:------------- |
||
|These statements should only be used if they give higher readability than their structured counterparts.|
<br>

|<span style="background-color:lightblue"> 60. The form *while(true)* should be used for infinite loops. </span>|
|:------------- |
|<pre>while (true) { <br>  : <br>} <br><br>for (;;) {  // NO! <br>  : <br>} <br> <br>while (1) { // NO! <br>  : <br>} </pre>|
|Testing against 1 is neither necessary nor meaningful. The form *for (;;)* is not very readable, and it is not apparent that this actually is an infinite loop.|
<br>

### <a name="StatementsConditionals"></a> 5.4 Conditionals

|<span style="background-color:lightblue"> 61. Complex conditional expressions must be avoided. Introduce temporary boolean variables instead [[1](#reference1)]. </span>|
|:------------- |
|<pre>bool isFinished = (elementNo < 0) &#124;&#124; (elementNo > maxElement); <br>bool isRepeatedEntry = elementNo == lastElement; <br>if (isFinished &#124;&#124; isRepeatedEntry) { <br>  : <br>} <br> <br>// NOT: <br>if ((elementNo < 0) &#124;&#124; (elementNo > maxElement) &#124;&#124; <br>     elementNo == lastElement) { <br>  : <br>} </pre>|
|By assigning boolean variables to expressions, the program gets automatic documentation. The construction will be easier to read, debug and maintain.|
<br>

|<span style="background-color:lightblue"> 62. The nominal case should be put in the *if*-part and the exception in the *else*-part of an if statement [[1](#reference1)]. </span>|
|:------------- |
|<pre>bool isOk = readFile (fileName); <br>if (isOk) { <br>  : <br>} <br>else { <br>  : <br>} </pre>|
|Makes sure that the exceptions don't obscure the normal path of execution. This is important for both the readability and performance.|
<br>

|<span style="background-color:lightblue"> 63. The conditional should be put on a separate line. </span>|
|:------------- |
|<pre>if (isDone)       // NOT: if (isDone) doCleanup(); <br>  doCleanup(); </pre>|
|This is for debugging purposes. When writing on a single line, it is not apparent whether the test is really true or not.|
<br>

|<span style="background-color:lightblue"> 64. Executable statements in conditionals must be avoided. </span>|
|:------------- |
|<pre>File* fileHandle = open(fileName, "w"); <br>if (!fileHandle) { <br>  : <br>} <br> <br>// NOT: <br>if (!(fileHandle = open(fileName, "w"))) { <br>  : <br>}</pre>|
|Conditionals with executable statements are just very difficult to read. This is especially true for programmers new to C/C++.|
<br>

### <a name="StatementsMiscellaneous"></a> 5.5 Miscellaneous

|<span style="background-color:lightblue"> 65. The use of magic numbers in the code should be avoided. Numbers other than 0 and 1 should be considered declared as named constants instead. </span>|
|:------------- |
||
|If the number does not have an obvious meaning by itself, the readability is enhanced by introducing a named constant instead. A different approach is to introduce a method from which the constant can be accessed.|
<br>

|<span style="background-color:lightblue"> 66. Floating point constants should always be written with decimal point and at least one decimal. </span>|
|:------------- |
|<pre> double total = 0.0;    // NOT:  double total = 0; <br>double speed = 3.0e8;  // NOT:  double speed = 3e8; <br> <br>double sum; <br>: <br>sum = (a + b) * 10.0; </pre>|
|This emphasizes the different nature of integer and floating point numbers. Mathematically the two model completely different and non-compatible concepts. <br><br>Also, as in the last example above, it emphasizes the type of the assigned variable (sum) at a point in the code where this might not be evident.|
<br>

|<span style="background-color:lightblue"> 67. Floating point constants should always be written with a digit before the decimal point. </span>|
|:------------- |
|<pre>double total = 0.5;  // NOT:  double total = .5; </pre>|
|The number and expression system in C++ is borrowed from mathematics and one should adhere to mathematical conventions for syntax wherever possible. Also, 0.5 is a lot more readable than .5; There is no way it can be mixed with the integer 5.|
<br>

|<span style="background-color:lightblue"> 68. Functions must always have the return value explicitly listed. </span>|
|:------------- |
|<pre>int getValue()   // NOT: getValue() <br>{ <br>  : <br>}</pre>|
|If not exlicitly listed, C++ implies int return value for functions. A programmer must never rely on this feature, since this might be confusing for programmers not aware of this artifact.|
<br>

|<span style="background-color:lightblue"> 69. *goto* should not be used. </span>|
|:------------- |
||
|Goto statements violate the idea of structured code. Only in some very few cases (for instance breaking out of deeply nested structures) should goto be considered, and only if the alternative structured counterpart is proven to be less readable.|
<br>

|<span style="background-color:lightblue"> 70. "0" should be used instead of "*NULL*". </span>|
|:------------- |
||
|*NULL* is part of the standard C library, but is made obsolete in C++.|
<br>

## <a name="LayoutAndComments"></a> 6 Layout and Comments

### <a name="LayoutAndCommentsLayout"></a> 6.1 Layout

|<span style="background-color:lightblue">  </span>|
|:------------- |
|<pre> <br> </pre>|
||
<br>

|<span style="background-color:lightblue">  </span>|
|:------------- |
|<pre> <br> </pre>|
||
<br>

|<span style="background-color:lightblue">  </span>|
|:------------- |
|<pre> <br> </pre>|
||
<br>

|<span style="background-color:lightblue">  </span>|
|:------------- |
|<pre> <br> </pre>|
||
<br>

|<span style="background-color:lightblue">  </span>|
|:------------- |
|<pre> <br> </pre>|
||
<br>

|<span style="background-color:lightblue">  </span>|
|:------------- |
|<pre> <br> </pre>|
||
<br>

|<span style="background-color:lightblue">  </span>|
|:------------- |
|<pre> <br> </pre>|
||
<br>

|<span style="background-color:lightblue">  </span>|
|:------------- |
|<pre> <br> </pre>|
||
<br>

## <a name="references"></a> 7 References

<a name="reference1"></a> [1] Code Complete, Steve McConnell - Microsoft Press

<a name="reference2"></a> [2] Programming in C++, Rules and Recommendations, M Henricson, e. Nyquist,  Ellemtel (Swedish telecom) 
      [http://www.doc.ic.ac.uk/lab/cplus/c%2b%2b.rules/](http://www.doc.ic.ac.uk/lab/cplus/c%2b%2b.rules/)

<a name="reference3"></a> [3] Wildfire C++ Programming Style, Keith Gabryelski, Wildfire Communications Inc. 
      [http://www.wildfire.com/~ag/Engineering/Development/C++Style/](http://www.wildfire.com/~ag/Engineering/Development/C++Style/)

<a name="reference4"></a> [4] C++ Coding Standard, Todd Hoff 
      [http://www.possibility.com/Cpp/CppCodingStandard.htm](http://www.possibility.com/Cpp/CppCodingStandard.htm)

<a name="reference5"></a> [5] Doxygen documentation system 
      [http://www.stack.nl/~dimitri/doxygen/index.html](http://www.stack.nl/~dimitri/doxygen/index.html)
