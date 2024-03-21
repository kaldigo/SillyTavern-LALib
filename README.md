# LALib

Library of STScript commands.

```
/lalib? 
– Lists LALib commands


/test left=val rule=rule right=val
– Returns true or false, depending on whether left and right adhere to rule. Available rules: gt => a > b, gte => a >= b, lt => a < b, lte => a <= b, eq => a == b, neq => a != b, not => !a, in (strings) => a includes b, nin (strings) => a not includes b

/and left=val right=val
– Returns true if both left and right are true, otherwise false.

/or left=val right=val
– Returns true if at least one of left and right are true, false if both are false.

/not (value)
– Returns true if value is false, otherwise true.


/foreach [optional list=[1,2,3]] [optional var=varname] [optional globalvar=globalvarname] (/command {{item}} {{index}})
– Executes command for each item of a list or dictionary.

/map [optional list=[1,2,3]] [optional var=varname] [optional globalvar=globalvarname] (/command {{item}} {{index}})
– Executes command for each item of a list or dictionary and returns the list or dictionary of the command results.


/filter [optional list=[1,2,3]] [optional var=varname] [optional globalvar=globalvarname] (/command {{item}} {{index}})
– Executes command for each item of a list or dictionary and returns the list or dictionary of only those items where the command returned true.

/find [optional list=[1,2,3]] [optional var=varname] [optional globalvar=globalvarname] (/command {{item}} {{index}})
– Executes command for each item of a list or dictionary and returns the first item where the command returned true.


/dict [optional var=varname] [optional globalvar=globalvarname] (list of lists)
– Takes a list of lists (each item must be a list of at least two items) and creates a dictionary by using each items first item as key and each items second item as value.


/join [optional glue=", "] [optional var=varname] [optional globalvar=globalvarname] (optional list)
– Joins the items of a list with glue into a single string. Use glue={{space}} to join with a space.

/split [optional find=","] [optional trim=true|false] [optional var=varname] [optional globalvar=globalvarname] (value)
– Splits value into list at every occurrence of find. Supports regex find=/\s/


/trim (text to trim)
– Removes whitespace at the start and end of the text.


/slice start=int [optional end=int] [optional length=int] [optional var=varname] [optional globalvar=globalvarname] (optional value)
– Retrieves a slice of a list or string.

/shuffle (list to shuffle)
– Returns a shuffled list.


/getat index=int|fieldname|list [optional var=varname] [optional globalvar=globalvarname] (optional value)
– Retrieves an item from a list or a property from a dictionary.

/setat index=int|fieldname|list [optional var=varname] [optional globalvar=globalvarname] [optional value=list|dictionary] (value)
– Sets an item in a list or a property in a dictionary. Example: /setat value=[1,2,3] index=1 X returns [1,"X",3], /setat var=myVariable index=[1,2,"somePropery"] foobar sets the value of myVariable[1][2].someProperty to "foobar" (the variable will be updated and the resulting value of myVariable will be returned). Can be used to create structures that do not already exist.


/try (command)
– try catch.

/catch [pipe={{pipe}}] (command)
– try catch. You must always set pipe={{pipe}} and /catch must always be called right after /try. Use {{exception}} or {{error}} to get the exception's message.


/copy (value)
– Copies value into clipboard.

/download [optional name=filename] [optional ext=extension] (value)
– Downloads value as a text file.


/dom [action=click|value|property] [optional value=newValue] [optional property=propertyName] [optional attribute=attributeName] (CSS selector)
– Click on an element, change its value, retrieve a property, or retrieve an attribute. To select the targeted element, use CSS selectors. Example: /dom action=click #expandMessageActions or /dom action=value value=0 #avatar_style


/memberpos (name) (position)
– Move group member to position (index starts with 0).


/switch [optional var=varname] [optional globalvar=globalvarname] (optional value)
– Use with /case.

/case [pipe={{pipe}}] [value=comparisonValue] (/command)
– Execute command and break out of the switch if the value given in /switch matches the value given here.


/ife (/command)
– Use with /then, /elseif, and /else. The provided command must return true or false.

/elseif [pipe={{pipe}}] (/command)
– Use with /ife, /then, and /else. The provided command must return true or false.

/else [pipe={{pipe}}] (/command)
– Use with /ife, /elseif, and /then. The provided command will be executed if the previous /if or /elseif was false.

/then [pipe={{pipe}}] (/command)
– Use with /ife, /elseif, and /else. The provided command will be executed if the previous /if or /elseif was true.


/wi-list-entries [optional flat=true] (optional book name)
– Get a list of World Info entries from currently active books or from the book with the provided name. Use flat=true to list all entrie in a flat list instead of a dictionary with entries per book.


/fetch (url)
– UNDOCUMENTED

/$ [optional query=cssSelector] [optional take=property] [optional call=property] (html)
– UNDOCUMENTED

/$$ [optional query=cssSelector] [optional take=property] [optional call=property] (html)
– UNDOCUMENTED
```
