# Inflector pluralizes and singularizes English nouns. It also contains some other useful methods.

###### string `Inflector::pluralize(string $word)`
Converts a word to its plural form. Note that this is for English only!

For example, 'apple' will become 'apples', and 'child' will become 'children'.
-param string $word the word to be pluralized

###### string `Inflector::singularize(string $word)`
Returns the singular of the $word.
- param string $word the english word to singularize

###### string `Inflector::titleize(string $word [, bool $ucAll = false])`
Converts an underscored or CamelCase word into a English sentence.
- param string $words
- param $ucAll whether to set all words to uppercase

###### string `Inflector::camelize(string $word)`
Converts a word like "send_email" to "SendEmail". It will remove non alphanumeric character from the word, so "who's online" will be converted to "WhoSOnline".
- param string $word the word to CamelCase

###### string `Inflector::camel2words(string $word [, bool $ucwords = false])`
Converts a CamelCase name into space-separated words.

For example, 'PostTag' will be converted to 'Post Tag'.
- param string $name the string to be converted
- param bool $ucwords whether to capitalize the first letter in each word
- param $ucwords whether to capitalize the first letter in each word.
 
###### string `Inflector::camel2id(string $name [, string $separator = '-' [, bool $strict = false]])`
Converts a CamelCase name into an ID in lowercase. Words in the ID may be concatenated using the specified character (defaults to '-').

For example, 'PostTag' will be converted to 'post-tag'.
- param string $name the string to be converted
- param string $separator the character used to concatenate the words in the ID
- param bool|string $strict whether to insert a separator between two consecutive uppercase chars, defaults to false

###### string `Inflector::id2camel(string $id [, string $separator = '-'])`
Converts an ID into a CamelCase name. Words in the ID separated by `$separator` (defaults to '-') will be concatenated into a CamelCase name.

For example, 'post-tag' is converted to 'PostTag'.

- param string $id the ID to be converted
- param string $separator the character used to separate the words in the ID

###### string `Inflector::underscore(string $words)`
Converts any "CamelCased" into an "underscored_word".
- param string $words the word(s) to underscore

###### string `Inflector::humanize(string $word [, bool $ucAll = false])`
Returns a human-readable string from $word.
- param string $word the string to humanize
- param bool $ucAll whether to set all words to uppercase or not

###### string `Inflector::variablize(string $word)`
Same as camelize but first char is in lowercase.
Converts a word like "send_email" to "sendEmail". It will remove non alphanumeric character from the word, so "who's online" will be converted to "whoSOnline".
- param string $word to lowerCamelCase

###### string `Inflector::tableize(string $className)`
Converts a class name to its table name (pluralized) naming conventions.

For example, converts "Person" to "people".
- param string $className the class name for getting related table_name

###### string `Inflector::slug(string $name [, string $replacement = '-' [, bool $lowercase = true]])`
Returns a string with all spaces converted to given replacement, non word characters removed and the rest of characters transliterated.

If intl extension isn't available uses fallback that converts latin characters only and removes the rest. You may customize characters map via $transliteration property of the helper.
- param string $string An arbitrary string to convert
- param string $replacement The replacement to use for spaces
- param bool $lowercase whether to return the string in lowercase or not. Defaults to `true`.

###### string `Inflector::transliterate(string $string [, string|\Transliterator $transliterator = null])`
Returns transliterated version of a string.

If intl extension isn't available uses fallback that converts latin characters only and removes the rest. You may customize characters map via $transliteration property of the helper.
- param string $string input string
- param string|\Transliterator $transliterator either a [[\Transliterator]] or a string from which a [[\Transliterator]] can be built.

###### string `Inflector::classify(string $tableName)`  
Converts a table name to its class name.

For example, converts "people" to "Person".
- param string $tableName

###### string `Inflector::ordinalize(int $number)`
Converts number to its ordinal English form. For example, converts 13 to 13th, 2 to 2nd ...
- param int $number the number to get its ordinal value

###### string `Inflector::sentence(array $words [, $twoWordsConnector = ' and ' [, $lastWordConnector = null [, $connector = ', ']]])`
Converts a list of words into a sentence.

Special treatment is done for the last few words. For example,

```php
$words = ['Spain', 'France'];
echo Inflector::sentence($words);
// output: Spain and France

$words = ['Spain', 'France', 'Italy'];
echo Inflector::sentence($words);
// output: Spain, France and Italy

$words = ['Spain', 'France', 'Italy'];
echo Inflector::sentence($words, ' & ');
// output: Spain, France & Italy
```

- param array $words the words to be converted into an string
- param string $twoWordsConnector the string connecting words when there are only two
- param string $lastWordConnector the string connecting the last two words. If this is null, it will take the value of `$twoWordsConnector`.
- param string $connector the string connecting words other than those connected by $lastWordConnector and $twoWordsConnector
