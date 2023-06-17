# Regex Tutorial

This tutorial aims to provide a comprehensive breakdown and explanation of one of regex pattern in order to help web development students understand its search pattern. Regular expressions, commonly known as regex, are sequences of characters used to define specific search patterns. They are extensively utilized by developers to find patterns within strings, replace characters or sequences, and validate input.

In this tutorial, we will dive into the intricacies of the Matching an Email and explore each component in detail. By the end, you will have a solid understanding of how the regex functions and how its individual parts contribute to defining the search pattern.


## Summary of the Regex Pattern: Matching an Email

The chosen regex pattern for this tutorial is designed to match and validate email addresses. Emails are widely used in various web applications, and it's essential to ensure that user input adheres to a valid email format. The provided regex pattern /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ incorporates multiple components to accurately validate an email address. By understanding each component and its role, developers can efficiently utilize this regex pattern to validate user input and ensure the integrity of email data.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components
**Component 1: ^([a-z0-9_\.-]+)**

This component ensures that the email address starts with a valid username. It allows a combination of lowercase letters, numbers, underscores, dots, and hyphens. The + indicates that one or more characters from the defined set can be present.

For example:

The username "john.doe" satisfies this component.
The username "johndoe123" also satisfies this component.
However, the username "john@doe" would not match this component since it contains the @ symbol, which is not allowed in the username.

**Component 2: @([\da-z\.-]+)**

This component verifies the presence of the @ symbol and ensures that the domain name follows it. The domain name can consist of lowercase letters, numbers, dots, and hyphens. The + indicates that one or more characters from the defined set can be present.

For example:

The email address "john.doe@example.com" satisfies this component, with the domain name "example.com" following the @ symbol.
The email address "johndoe123@gmail.com" also satisfies this component, with the domain name "gmail.com" following the @ symbol.
However, the email address "john.doe" would not match this component since it lacks the @ symbol.

**Component 3: \.([a-z\.]{2,6})$**

This component verifies the top-level domain (TLD) of the email address, such as ".com" or ".org." It ensures that the TLD consists of lowercase letters and dots, with a length between 2 and 6 characters.

For example:

The email address "john.doe@example.com" satisfies this component, with the TLD "com" matching the pattern.
The email address "johndoe123@gmail.co.uk" also satisfies this component, with the TLD "co.uk" matching the pattern.
However, the email address "john.doe@example" would not match this component since the TLD length is less than 2 characters.
  
### Anchors

Anchors are special characters in regular expressions that allow us to specify the position of a match within a string. In the email regex pattern /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/, we utilize two anchors: the ^ (caret) and the $ (dollar sign).

- The ` ^ ` anchor denotes the start of the string. In our email regex pattern, it ensures that the match starts from the beginning of the input. This means that the email address should not have any preceding characters before the username.

For example:

The email address "john.doe@example.com" satisfies this requirement since the match starts immediately after the ^ anchor.
However, the email address " john.doe@example.com" (with preceding spaces) would not match this pattern since the ^ anchor mandates a match at the start of the string.


- On the other hand, the ` $ ` anchor represents the end of the string. It ensures that the match extends until the end of the input. In the email regex pattern, it guarantees that the TLD (top-level domain) is the final component of the email address and that no characters follow it.

For example:

The email address "john.doe@example.com" satisfies this requirement since the match ends immediately before the $ anchor.
However, the email address "john.doe@example.com " (with trailing spaces) would not match this pattern since the $ anchor demands a match at the end of the string.

By using the ^ and $ anchors appropriately, we can precisely define the boundaries of the email address within the input string and ensure that it conforms to the desired structure.

### Quantifiers

Quantifiers are special characters in regular expressions that specify the quantity or repetition of a preceding element. They allow us to define how many times a particular character or group of characters should occur. In the email regex pattern /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/, we utilize two main quantifiers: + (plus) and {2,6}.

- The ` + ` quantifier indicates that the preceding element should occur one or more times. In our email regex pattern, it applies to the username and domain sections, [a-z0-9_\.-]+ and [\da-z\.-]+ respectively. These sections allow for a combination of lowercase letters, numbers, underscores, dots, and hyphens.

For example:

The email address "john.doe@example.com" satisfies this quantifier since the username "john.doe" and the domain "example" both have one or more characters.
However, the email address "j@e.com" would not match this pattern since the username and domain do not meet the requirement of one or more characters.


- The ` {2,6} ` quantifier specifies a range of occurrences for the preceding element. In our email regex pattern, it applies to the TLD section [a-z\.]{2,6}, ensuring that the TLD consists of 2 to 6 lowercase letters or dots.

For example:

The email address "john.doe@example.com" satisfies this quantifier since the TLD "com" falls within the specified range of 2 to 6 characters.
However, the email address "john.doe@example" would not match this pattern since the TLD "example" exceeds the maximum limit of 6 characters.


### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

The OR operator, denoted by the ` | ` symbol, provides the ability to express alternatives within a regular expression. It allows us to define multiple patterns, and if any of those patterns match, the regex will consider it a successful match. In the email regex pattern /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/, the OR operator is not explicitly utilized. However, it can be useful in other scenarios when working with regular expressions.

For example, if we wanted to match email addresses that end with either ".com" or ".net", we could modify the TLD section of the regex pattern using the OR operator as follows: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.(com|net)$/.

In this modified pattern, (com|net) signifies that the TLD can be either "com" or "net". The OR operator allows us to create a choice between the two options. If the TLD matches either "com" or "net", the email address will be considered a match.

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
