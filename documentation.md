---
layout: page
title :
header : Documentation
group: navigation
---
{% include JB/setup %}



<div class="short docs">
<div class="wrapper-color-content">

<h3>Documentation</h3>
<h4>Poor software <span class="bold">doesn't have</span> documentation.
Brilliant software <span class="bold">doesn't need</span> documentation.</h4>

We are proud to claim that Selenide is so simple that you don't need to read tons of documentation.<br/>
The whole work with Selenide consists of three simple things! <br>
</div></div>

<div class="quicklinks">
<div class="wrapper-color-content">
<ul class="gray-boxes">
  <li><a href="https://github.com/codeborne/selenide" target="_blank"><span class="ql"><h3>View on</h3> <strong><h4>GitHub</h4></strong></span></a></li>
  <li><a href="http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.codeborne%22%20AND%20a%3A%22selenide%22" target="_blank"><span class="ql"><h3>Search in</h3> <strong><h4>Maven</h4></strong></span></a></li>
  <li><a href="{{ BASE_PATH }}/archive.html"><span class="ql"><h3>Read our</h3> <strong><h4>Blog</h4></strong></span></a></li>
  <li><a href="http://twitter.com/jselenide" target="_blank"><span class="ql"><h3>Follow at</h3><strong><h4>Twitter</h4></strong></span></a></li>
  <li><a href="{{ BASE_PATH }}/rss.xml"><span class="ql"><h3>Subscribe to</h3><strong><h4>RSS</h4></strong></span></a></li>
</ul>
</div>
</div>
<div class="wrapper-content">
## Three simple things:
<strong>1.</strong>  Open the page   <br>
<strong>2.</strong>  $(find element).doAction()<br>
<strong>3.</strong>  $(find element).checkCondition()<br>

```java
  open("/login");
  $("#submit").click();
  $(".message").shouldHave(text("Hello"));
```

## Use the power of IDE

Selenide API consists of few classes. We suggest you to stop reading, open your IDE and start typing.

Just type: `$(selector).` - and IDE suggest you all the options.

<img src="{{ BASE_PATH }}/images/ide-just-start-typing.png" alt="Selenide API: Just start typing"/>

Use the power of nowdays development environments instead of bothering with documentation!

<br/>

## Selenide API

Here is a full <a href="/javadoc/2.4" target="_blank">Selenide javadoc</a>.

Just for reference, these are Selenide classes you will probably need for work:

<h3>com.codeborne.selenide.Selenide
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/Selenide.java">[src]</a>
  <a target="_blank" href="{{ BASE_PATH }}/javadoc/2.4/com/codeborne/selenide/Selenide.html">[javadoc]</a>
</h3>

The main class for using Selenide library. Two basic methods are `open` and `dollar`:
<ul>
  <li><a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/Selenide.html#open(java.lang.String)">open(URL)</a>, and</li>
  <li><a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/Selenide.html#$(java.lang.String)">$(String cssSelector)</a>   - returns SelenideElement</li>
  <li><a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/Selenide.html#$(org.openqa.selenium.By)">$(By)</a>   - returns SelenideElement</li>
  <li><a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/Selenide.html#$$(java.lang.String)">$$(String cssSelector)</a>   - returns collection of elements</li>
  <li><a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/Selenide.html#$$(org.openqa.selenium.By)">$$(By)</a>   - returns collection of elements</li>
</ul>

When received a SelenideElement instance, you can either do action with it (`click`, `setValue`) or
check a condition: `shouldHave(text("abc"))`.

There is also a number of other less frequently used methods in Selenide class:
<a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/Selenide.html#sleep(long)">sleep()</a>,
<a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/Selenide.html#refresh()">refresh()</a> and
<a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/Selenide.html#title()">title()</a>.

<h3>com.codeborne.selenide.SelenideElement
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/SelenideElement.java">[src]</a>
  <a target="_blank" href="{{ BASE_PATH }}/javadoc/2.4/com/codeborne/selenide/SelenideElement.html">[javadoc]</a>
</h3>

SelenideElement is a wrapper around Selenium WebElement, giving it some additional convenient method:

*  should(Condition)
*  shouldBe(Condition)
*  shouldHave(Condition)
*  shouldNot(Condition)
*  shouldNotBe(Condition)
*  shouldNotHave(Condition)<br/>
*  waitUntil(Condition, milliseconds)
*  waitWhile(Condition, milliseconds)<br/>
*  find(String | By)
*  findAll(String | By)<br/>
*  setValue(String)
*  val(String)
*  append(String)
*  pressEnter(String)<br/>
*  val()
*  data()
*  text()
*  isDisplayed()
*  exists()<br/>
*  selectOption(String text)
*  selectOptionByValue(String value)
*  getSelectedOption()
*  getSelectedText()
*  getSelectedValue()<br/>
*  uploadFromClasspath(String fileName)
*  toWebElement()

<h3>com.codeborne.selenide.Condition
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/Condition.java">[src]</a>
  <a target="_blank" href="{{ BASE_PATH }}/javadoc/2.4/com/codeborne/selenide/Condition.html">[javadoc]</a>
</h3>


*   visible | appear   // e.g. $("input").shouldBe(visible)
*   present | exist
*   hidden | disappear | not(visible)
*   readonly           // e.g. $("input").shouldBe(readonly)
*   attribute(String)
*   name               // e.g. $("input").shouldHave(name("fname"))
*   value              // e.g. $("input").shouldHave(value("John"))
*   type               // $("#input").shouldHave(type("checkbox"))
*   id                 // $("#input").shouldHave(id("myForm"))
*   empty              // $("h2").shouldBe(empty)
*   options
*   cssClass(String)
*   focused
*   enabled
*   disabled
*   selected
*   matchText(String regex)
*   text(String substring)
*   exactText(String wholeText)
*   textCaseSensitive(String substring)
*   exactTextCaseSensitive(String wholeText)

You can easily add your own conditions by implementing interface `com.codeborne.selenide.Condition`


<h3>com.codeborne.selenide.Selectors
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/Selectors.java">[src]</a>
  <a target="_blank" href="{{ BASE_PATH }}/javadoc/2.4/com/codeborne/selenide/Selectors.html">[javadoc]</a>
</h3>

This class contains some `By` selectors for searcing elements by text or attribute (that are missing in standard Selenium WebDriver API):

*   <a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/Selectors.html#byText(java.lang.String)">byText</a>     - search by text (substring)
*   <a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/Selectors.html#withText(java.lang.String)">withText</a>   - search by exact text
*   <a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/Selectors.html#by(java.lang.String, java.lang.String)">by</a>    - search by attribute
*   <a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/Selectors.html#byTitle(java.lang.String)">byTitle</a>   - search by "title" attribute
*   <a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/Selectors.html#byValue(java.lang.String)">byValue</a>   - search by "value" attribute

<h3>com.codeborne.selenide.ElementsCollection
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/ElementsCollection.java">[src]</a>
  <a target="_blank" href="{{ BASE_PATH }}/javadoc/2.4/com/codeborne/selenide/ElementsCollection.html">[javadoc]</a>
</h3>

This is the class returned by `$$` method. It contains a list of web elements with additionals methods:

*   <a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/ElementsCollection.html#shouldBe(com.codeborne.selenide.CollectionCondition)">shouldBe</a>     - e.g. `$$(".errors").shouldBe(empty)`
*   <a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/ElementsCollection.html#shouldHave(com.codeborne.selenide.CollectionCondition)">shouldHave</a>     - e.g. `$$("#mytable tbody tr").shouldHave(size(2))`
*   <a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/ElementsCollection.html#find(com.codeborne.selenide.Condition)">find</a>     - e.g. `$$("#multirowTable tr").findBy(text("Norris"))`
*   <a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/ElementsCollection.html#filter(com.codeborne.selenide.Condition)">filter</a>     - e.g. `$$("#multirowTable tr").filterBy(text("Norris"))`
*   <a href="{{BASE_PATH}}/javadoc/2.4/com/codeborne/selenide/ElementsCollection.html#exclude(com.codeborne.selenide.Condition)">exclude</a>     - e.g. `$$("#multirowTable tr").excludeWith(text("Chack"))`


To be continued...

<h3>com.codeborne.selenide.CollectionCondition
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/CollectionCondition.java">[src]</a>
  <a target="_blank" href="{{ BASE_PATH }}/javadoc/2.4/com/codeborne/selenide/CollectionCondition.html">[javadoc]</a>
</h3>

<h3>com.codeborne.selenide.WebDriverRunner
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/WebDriverRunner.java">[src]</a>
  <a target="_blank" href="{{ BASE_PATH }}/javadoc/2.4/com/codeborne/selenide/WebDriverRunner.html">[javadoc]</a>
</h3>

<h3>com.codeborne.selenide.WebDriverProvider
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/WebDriverProvider.java">[src]</a>
  <a target="_blank" href="{{ BASE_PATH }}/javadoc/2.4/com/codeborne/selenide/WebDriverProvider.html">[javadoc]</a>
</h3>

<h3>com.codeborne.selenide.Configuration
  <a target="_blank" href="https://github.com/codeborne/selenide/blob/master/src/main/java/com/codeborne/selenide/Configuration.java">[src]</a>
  <a target="_blank" href="{{ BASE_PATH }}/javadoc/2.4/com/codeborne/selenide/Configuration.html">[javadoc]</a>
</h3>



Stay tuned!