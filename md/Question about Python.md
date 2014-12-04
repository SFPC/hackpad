# Question about Python

Sharing an ongoing conversation with Zach about Python for parsing, sorting data:

I'm now working with the raw data from ingredients to find pattern of shared compounds.

Here is my question:

as you can see in the attached file I have a csv with 2 columns, ingredients id and compounds id.

Ingredients that contain more than one compounds are repeated several times.

I'd like to find out the ingredients that are repeated the most (the most frequent ==> ingredients with a lot of compounds) and sort my list from "most repeated ingredients" to "least repeated ingredients". (of course I want to keep the compounds info as well next to ingredient id)

So far my understanding is: I need to create a dictionary from the csv, and look for repeated ingredients and eventually sort them.

*   see below, I think you need a<u> dictionary of sets</u> (your ingredients are the key in the dictionary, the sets are the value which are a unique list of compounds per ingredient)

Here is where I am stuck with the code, any tip/suggestion?

here is the link with Python code + data set:

[](https://www.dropbox.com/sh/kvy8y5w1hoj1q25/kkQpG0t1jS)https://www.dropbox.com/sh/kvy8y5w1hoj1q25/kkQpG0t1jS

*   import_ingredients_compounds_b (python script)
*   ingr_comp.csv (csv file with relationship between ingredients id and compounds id, if an ingredient contains more than a compound it is repeated)
*   ingr_info_b.csv (csv file with ingredients id and correspondent ingredient name)
*   comp_info.tsv (tsv file with compounds id and correspondent compound name)

//------------------------------------------------

I think the best way to do this is via a map (key value pair) -- here's a small example that counts the compounds per ingredient and reports them in numerical order: 

[](http://pastebin.com/m0D3JgyS)[http://pastebin.com/m0D3JgyS](http://pastebin.com/m0D3JgyS)

I really like the collection.counter object for this: 

*   _A Counter is a dict[ionary] subclass for counting hashable objects. It is an unordered collection where elements are stored as dictionary keys and their counts are stored as dictionary values. _

the heart of this code is here -- think of ingredients as a key value map, where you can access the array by name not integer...  

*   ingredients[row['ingredient id']] += 1

key value stores are basically like: 

*   ingredients[205] = 124;

where "205" isn't the position in the array (!!!), but actually a unique identifier (and in this case, the 124 is the count).  here's a p5 example which might be easier to understand: 

[](http://processing.org/reference/HashMap.html)[http://processing.org/reference/HashMap.html](http://processing.org/reference/HashMap.html)

for trying to wrap your head around hashes.  for counting, this is really useful idea.  what I like is the "most common" function, which prints out things like: 

*   print ingredients.most_common(10)

*   [('908', 239), ('631', 234), ('506', 230), ('1495', 227), ('1428', 222), ('360', 217), ('258', 216), ('625', 206), ('958', 204), ('248', 199)]

this is the 10 ingredients that have the most compounds associated with them. 

the next step is to build a dictionary as well as we parse, and use the results of this counter to look up from the dictionary. 

for a data structure what I think you really want is a **dictionary of sets**.  a set is like an array but where each object is unique, in your case, your compound for each ingedient is unique, and each ingedient needs to have more then one compound. 

googling, I got to this: 

[](http://stackoverflow.com/questions/2285874/python-dictionary-that-maps-strings-to-a-set-of-strings/2285881#2285881)[http://stackoverflow.com/questions/2285874/python-dictionary-that-maps-strings-to-a-set-of-strings/2285881#2285881](http://stackoverflow.com/questions/2285874/python-dictionary-that-maps-strings-to-a-set-of-strings/2285881#2285881)

I implemented this, 

[](http://pastebin.com/P1Z1K6Pt)[http://pastebin.com/P1Z1K6Pt](http://pastebin.com/P1Z1K6Pt)

which 

(a) prints out the top ten ingredients

(b) for each top ten ingredients, prints out the set associated with it (all the unique compounds it has)

output looks like: 

[('908', 239), ('631', 234), ('506', 230), ('1495', 227), ('1428', 222), ('360', 217), ('258', 216), ('625', 206), ('958', 204), ('248', 199)]

908

set([' 609', ' 58', ' 786', ' 784', ' 196', ' 292', ' 50', ' 52', ' 554', ' 822', ' 1007', ' 1004', ' 1005', ' 826', ' 827', ' 1084', ' 578', ' 1080', ' 577', ' 628', ' 573', ' 275', ' 397', ' 273', ' 925', ' 170', ' 173', ' 174', ' 943', ' 177', ' 836', ' 945', ' 400', ' 737', ' 0', ' 1', ' 6', ' 1092', ' 1033', ' 8', ' 369', ' 777', ' 565', ' 243', ' 247', ' 163', ' 481', ' 249', ' 164', ' 841', ' 846', ' 847', ' 848', ' 580', ' 1101', ' 413', ' 720', ' 1078', ' 689', ' 724', ' 415', ' 1100', ' 682', ' 857', ' 680', ' 922', ' 600', ' 559', ' 606', ' 1002', ' 550', ' 317', ' 556', ' 311', ' 158', ' 159', ' 63', ' 62', ' 390', ' 391', ' 67', ' 69', ' 398', ' 954', ' 995', ' 697', ' 691', ' 690', ' 693', ' 858', ' 541', ' 540', ' 912', ' 1089', ' 424', ' 911', ' 549', ' 423', ' 756', ' 996', ' 994', ' 753', ' 893', ' 616', ' 611', ' 610', ' 387', ' 229', ' 75', ' 380', ' 220', ' 223', ' 224', ' 227', ' 963', ' 1040', ' 657', ' 17', ' 19', ' 909', ' 442', ' 308', ' 439', ' 426', ' 1055', ' 427', ' 704', ' 435', ' 985', ' 1023', ' 1104', ' 980', ' 667', ' 136', ' 1013', ' 139', ' 235', ' 971', ' 20', ' 1079', ' 22', ' 978', ' 875', ' 990', ' 521', ' 326', ' 288', ' 524', ' 345', ' 1091', ' 282', ' 283', ' 772', ' 771', ' 203', ' 775', ' 673', ' 445', ' 670', ' 440', ' 676', ' 675', ' 209', ' 127', ' 126', ' 548', ' 410', ' 519', ' 121', ' 90', ' 91', ' 93', ' 95', ' 1102', ' 1068', ' 1069', ' 961', ' 929', ' 33', ' 928', ' 1064', ' 37', ' 1082', ' 299', ' 298', ' 645', ' 357', ' 517', ' 806', ' 807', ' 800', ' 294', ' 211', ' 885', ' 198', ' 595', ' 215', ' 764', ' 767', ' 766', ' 761', ' 599', ' 384', ' 116', ' 115', ' 118', ' 884', ' 793', ' 794', ' 958', ' 798', ' 957', ' 45', ' 886', ' 184', ' 340', ' 346', ' 183', ' 1015', ' 658', ' 813', ' 811', ' 1095', ' 896', ' 895', ' 585', ' 584', ' 890', ' 462', ' 460', ' 466', ' 734', ' 716', ' 717', ' 735', ' 927', ' 107', ' 269', ' 103'])

this means, for ingredient 908 here are the compounds listed as a set.  you should notice the set is unsorted, but it's also **unique** which means that if a compound appears multiple times for an ingredient it wont appear in this list.

there's **great** property of sets which is if you want to see what compounds two sets have in common, for example, take two sets and compute the union / intersection, etc: 

[](http://docs.python.org/2/library/sets.html)[http://docs.python.org/2/library/sets.html](http://docs.python.org/2/library/sets.html)

(see 8.7.2. Example) 

I hope this helps

(side note, here's a nice counting example in python for word frequency: [](https://gist.github.com/bradmontgomery/4717521)[https://gist.github.com/bradmontgomery/4717521](https://gist.github.com/bradmontgomery/4717521)  and this is a nice explanation of operations on sets, which can be useful for figuring out how much commonality, difference etc there are between sets: 

[](https://www.khanacademy.org/math/probability/independent-dependent-probability/basic_set_operations/v/intersection-and-union-of-sets))https://www.khanacademy.org/math/probability/independent-dependent-probability/basic_set_operations/v/intersection-and-union-of-sets)

//------------------------------------------------