# AllAboutRegexInJavaAutomation
Regular expressions (regex) in Java provide a powerful way to define string patterns for searching, manipulating, and validating text. They are implemented in the java.util.regex package, primarily through the Pattern and Matcher classes. 

📌 Regular Expressions (Regex) in Java – For Automation Testing

Regular Expressions help in string validation, pattern matching, dynamic locators, API response parsing, and data extraction during automation.

This section summarizes every important regex concept used in automation frameworks.

✅ 1. Why Regex is Important in Automation?

Validate email, phone, ID formats

Extract dynamic values from API responses

Clean/format strings

Handle dynamic locators in Selenium

Validate logs & error messages

Filter data from large strings / JSON / logs

✅ 2. Basic Regex Syntax (Most Used)
Pattern	Meaning
.	Any character
\d	Digit (0–9)
\D	Non-digit
\w	Word character (A–Z, a–z, 0–9, _)
\W	Non-word character
\s	Space
^	Start of string
$	End of string
.*	Match anything
.+	One or more characters
?	Optional
{n}	Exactly n occurrences
{n,m}	Between n and m
[abc]	a or b or c
[a-z]	Range
`	`
( )	Grouping
✅ 3. Practical Automation Examples
🔹 Check if email format is valid
boolean isValid = Pattern.matches("^[A-Za-z0-9+_.-]+@(.+)$", email);

🔹 Extract ID from API response
Matcher m = Pattern.compile("\"id\":(\\d+)").matcher(jsonString);
if(m.find()) {
    String id = m.group(1);
}

🔹 Validate status code or numeric string
boolean isNumber = response.matches("\\d+");

🔹 Dynamic element selection (Selenium)
String name = "Login123";
driver.findElement(By.xpath("//input[@id='" + name.replaceAll("\\d","") + "']"));

✅ 4. Useful Regex Patterns for Automation
🔸 Email
^[A-Za-z0-9+_.-]+@(.+)$

🔸 Mobile Number
^[0-9]{10}$

🔸 UUID / GUID
^[a-fA-F0-9\\-]{36}$

🔸 Date Formats
\\d{4}-\\d{2}-\\d{2}

🔸 Only Alphabets
^[A-Za-z]+$

🔸 Only Numbers
^[0-9]+$

🔸 Alphanumeric
^[A-Za-z0-9]+$

🔸 Extract OTP from SMS/API
(\\d{4,6})

✅ 5. Java Code Template (Always Use This)
Pattern pattern = Pattern.compile("your-regex-here");
Matcher matcher = pattern.matcher(text);

while (matcher.find()) {
    System.out.println(matcher.group());
}

✅ 6. Tips For Automation Engineers

- Always escape backslashes in Java (\\d instead of \d)
- Use regex to avoid hardcoding values
- Use regex in assertions to verify dynamic responses
- Great for cleaning test data before processing
- Helps in verifying logs, error messages, XML/JSON blocks

📘 Summary
This section provides everything needed to use Regex professionally in Java test automation:

Syntax
Real automation examples
Ready-to-use patterns
Clean reusable template
