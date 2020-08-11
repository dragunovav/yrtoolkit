---
title: Voice Calculator
layout: tutorial
howtos: false
yrmedia: false
---

# Challenge

Have you ever wondered how conversational AI agents such as Alexa and Siri work?  How do they interpret what you are saying to them and grasp your intent?  How do they then know how to appropriately and meaningfully respond to you?  In this project you are challenged to create your very first own Voice User Interface (VUI) as you build a voice driven calculator that can do basic arithmetic operations.

# Setup your computer

<div class="setup" id="connect_app"></div>

# Voice Calculator (Level: Intermediate)

## Introduction



The purpose of this elementary level AI project is to give you a sense of the basics of a Voice User Interface (VUI) and to teach you how to design a simple AI system that can understand the intent of the user in a verbally stated calculation question and respond appropriately.


![GUI of Voice Calculator](../images/voiceCalculator/GUI.png){:.enlargeImage}


## Graphical User Interface (GUI)

The GUI has been created for you in the starter file.  Please change the properties of the components as you wish to get the look and feel you want.  However, please do not rename the components, as this tutorial will refer to the given names in the instructions.

![GUI of Voice Calculator](../images/voiceCalculator/GUICorrespondence.png){:.enlargeImage}

In the GUI you will notice that there is a Speak  button which the user will press to verbally communicate the calculation they wish to be performed.  The interface will then display in writing what the Calculator heard and respond, both in writing and verbally, with the result of the calculation.  If the Calculator could not hear a meaningful calculation query or could not understand the intent of the user, it will say so.


## Initialize <var>numberList</var>

The first thing you'll tackle is to extract the numbers in the sentence spoken by the user. You'll use them later when you actually perform the mathematical operation.  To do this first you will initialize a global variable named <var>numberList</var> where the numbers in the calculation query will be stored.  As this variable will be a list of numbers,  it will be initialized  to an empty list.


![Initialization of global numberList](../images/voiceCalculator/initialize_numberList.png){:.enlargeImage}

## procedure <var>extractNumbers</var> I

Then you  will create  a procedure  called <strong><var>extractNumbers</var></strong> which when given an input sentence will extract the numerical values in that sentence and store these in the global variable <var>numberList</var>.  To do this:
* choose a procedure and name it <strong><var>extractNumbers</var></strong>
* use the settings gear to add an input parameter and call it <var>sentence</var>


![procedure extractNumbers](../images/voiceCalculator/procedure_extractNumbers.png){:.enlargeImage}![procedure extractNumbers input parameter](../images/voiceCalculator/procedure_extractNumbers_inputParameter.png){:.enlargeImage}

(procedure continues next page)

## procedure <var>extractNumbers</var> II

* set the global variable <var>numberList</var> to the empty list.  We need to reinitialize the variable every time we call this procedure as each calculation the user initiates will use a new pair of numbers.
* use  the <strong>split at spaces</strong> text utility to split the input sentence into a list of  its words and for each word in this list check to see if it is a number.

![for each word ](../images/voiceCalculator/foreach_split.png){:.enlargeImage}

* if any word is a number then add it to the global variable <var>numberList</var>

<hint markdown="block" title="Give me a hint">

![procedure extractNumbers hint](../images/voiceCalculator/procedure_extractNumbers1.png){:.enlargeImage}

<hint markdown="block" title="Check my solution">

![procedure extractNumbers solution](../images/voiceCalculator/procedure_extractNumbers2.png){:.enlargeImage}

</hint>

</hint>

 Try this on your own but if you get stuck you can click the Hint button.


## Multiplication Intent
As there are many ways for a user to indicate that they would like to perform a multiplication operation, it is essential to identify all these different approaches as a multiplication intent.  For example all of the following statements are different ways of expressing a multiplication intent: 
* <span style="color:red">what is</span> <span style="color:green">73\*51</span> <span style="color:red">?</span>
* <span style="color:red">how much is</span> <span style="color:green">73x51</span><span style="color:red"> ?</span>
* <span style="color:red">what is the <span style="color:green">product</span> of</span> <span style="color:green">73</span> <span style="color:red">and</span> <span style="color:green">51</span> <span style="color:red">?</span>
* <span style="color:red">what is the result when you</span> <span style="color:green">multiply 73</span> <span style="color:red">with</span> <span style="color:green">51</span> <span style="color:red">?</span>
* <span style="color:red">what is</span> <span style="color:green">73 times 51</span> <span style="color:red">?</span>

Note that the key words/symbols/numbers in <span style="color:green">green</span> define the multiplication intent while the words/symbols in <span style="color:red">red</span> are redundant and can be disregarded.

## Boolean Procedures I
A Boolean procedure is a procedure that returns the values <strong>true</strong> or <strong>false</strong> based on the truth or falsity of the input statements.  

First, you will create a Boolean procedure with a return value called <strong><var>multiplicationIntended</var></strong> which will determine whether the user intends to perform a multiplication by checking for some key words in the sentence uttered by the user.

* choose a procedure with a return value and name it <strong><var>multiplicationIntended</var></strong>
* use the settings gear to add an input parameter and call it <var>sentence</var>
![procedure with return value](../images/voiceCalculator/procedureWithReturn.png){:.enlargeImage}
![procedure with input](../images/voiceCalculator/proceduremultiplicationIntendedwithinput.png){:.enlargeImage}

(procedure continues next page)

## Boolean Procedures II
* this procedure will return <strong>true</strong> if any of the following symbols/words: 

   { \*, x , product, multiply, times } 

   are contained in the sentence and will return <strong>false</strong> otherwise.  
<hint markdown="block" title="Give me a hint">

Note that Boolean text block <strong>contains</strong> can be used
<img src="../images/voiceCalculator/containstextpiece.png" alt="contains text block" style="width:50%">
for this purpose as well as  the logic operator <strong>or</strong> which can be utilized in a nested fashion.  
![logic block OR](../images/voiceCalculator/LogicOR.png){:.enlargeImage}
![logic block OR nested twice](../images/voiceCalculator/2NestedOR.png){:.enlargeImage}
![logic block OR nested three times](../images/voiceCalculator/3NestedOR.png){:.enlargeImage}

You can keep nesting as many <strong>or</strong> blocks as you need.  If any one of the nested <strong>or</strong> operators returns <strong>true</strong> then the collection returns <strong>true</strong>. 

<hint markdown="block" title="Check my solution">

![procedure multiplicationIntended solution](../images/voiceCalculator/procedure_multiplicationIntended.png){:.enlargeImage}

</hint>

</hint>

Try this on your own but if you get stuck you can click the Hint button.
 
## Boolean Procedures III
Now you will create three additional Boolean procedures in a similar fashion that will determine if the intended operation of the user is addition, subtraction or division.  Create these procedures but leave them blank for now.   Later, after testing that multiplication is being performed correctly, you will assemble these procedures in a very similar fashion to <strong><var>multiplicationIntended</var></strong>.

![procedure other operations intended](../images/voiceCalculator/otherOperationsIntended.png){:.enlargeImage}

## SpeakButton
Now you will write the code to give functionality to the Speak button.  When the Speak button is clicked:
* the <strong>UserTextLabel</strong> and <strong>CalculatorTextLabel</strong> are cleared
* call the <strong>SpeechRecognizer</strong> to get the text of what the user has spoken

<hint markdown="block" title="Give me a hint">

![when SpeakButton Click hint](../images/voiceCalculator/whenSpeakButtonClick1.png){:.enlargeImage}

<hint markdown="block" title="Check my solution">

![when SpeakButton Click solution](../images/voiceCalculator/whenSpeakButtonClick2.png){:.enlargeImage}

</hint>

</hint>
Try this on your own but if you get stuck you can click the Hint button.

## when SpeechRecognizer gets text I
When the <strong>SpeechRecognizer</strong> performs its task and returns with a text <var>result</var>:
* set the <strong>UserTextLabel</strong> to this text <var>result</var>.  This indicates what the Calculator heard.
* extract the numbers from the  text <var>result</var> to store them in the global variable <var>numberList</var>  using the procedure <strong><var>extractNumbers</var></strong>.
* set the <strong>CalculatorTextLabel</strong> to a default statement indicating that the Calculator could not understand what the user asked and inviting them to ask a clear calculation question.  For ex:  “I could not understand.  Please ask me a multiplication or addition or subtraction or division question like: What is 123 times 85?”

(procedure continues next page)

## when SpeechRecognizer gets text II
* check that there were exactly two numbers extracted from the sentence uttered by the user and if so, determine
	* if the intent was multiplication, set <strong>CalculatorTextLabel</strong> to the product of the two numbers
	* else if the intent was division, …… (leave blank for now)
	* else if the intent was addition, ….. (leave blank for now)
	* else if the intent was subtraction,  …..(leave blank for now)
* Use the <strong>TextToSpeech</strong> component to have the Calculator verbally read the contents of  the <strong>CalculatorTextLabel</strong>.

<hint markdown="block" title="Give me a hint">

![when SpeechRecognizer gets text hint](../images/voiceCalculator/whenSpeechRecognizer1AfterGettingText1.png){:.enlargeImage}

<hint markdown="block" title="Check my solution">

![when SpeechRecognizer gets text partial solution](../images/voiceCalculator/whenSpeechRecognizer1AfterGettingText2.png){:.enlargeImage}

</hint>

</hint>
Try this on your own but if you get stuck you can click the Hint button.

## Test your App for Multiplication

<img src="../images/voiceCalculator/AICompanion.png" style="width: 65%">

Now use the AI Companion to check that your app works well for a multiplication calculation.  Try to state your multiplication intent in a variety of ways to make sure that the Calculator responds properly with the correct product.  Also make a non-calculation statement like "Hello how are you doing today?" and check that the Calculator responds appropriately by saying "I could not understand.  Please ask me a multiplication or addition or subtraction or division question like: What is 123 times 85?"


## Other operations I
Now complete the three remaining Boolean procedures for the other operations: <strong><var>additionIntended</var></strong>, <strong><var>subtractionIntended</var></strong> and <strong><var>divisionIntended</var></strong>.  You can “copy and paste” the blocks of  the <strong><var>multiplicationIntended</var></strong>  procedure and make the appropriate changes for each operation.
![procedure other operations intended](../images/voiceCalculator/otherOperationsIntended.png){:.enlargeImage}

<hint markdown="block" title="Give me a hint">
The following symbols/words are common ways of indicating intent for each operation
* addition: { + , add, sum, plus}
* subtraction: { - , subtract, difference, minus}
* division: { /, ÷ , divide, quotient, ratio}

<hint markdown="block" title="Check my solution">

![procedure additionIntended solution](../images/voiceCalculator/procedure_additionIntended.png){:.enlargeImage}

![procedure subtractionIntended solution](../images/voiceCalculator/procedure_subtractionIntended.png){:.enlargeImage}

![procedure divisionIntended solution](../images/voiceCalculator/procedure_divisionIntended.png){:.enlargeImage}

</hint>

</hint>
Try this on your own but if you get stuck you can click the Hint button.

## Other operations II
And now complete the remaining parts of <strong>when SpeechRecognizer1.AfterGettingText</strong>

* else if the intent was division, set <strong>CalculatorTextLabel</strong> to the quotient of the two numbers
* else if the intent was addition, set <strong>CalculatorTextLabel</strong> to the sum of the two numbers
* else if the intent was subtraction, set <strong>CalculatorTextLabel</strong> to the difference of the two numbers

<hint markdown="block" title="Check my solution">

![when SpeechRecognizer gets text full solution](../images/voiceCalculator/whenSpeechRecongizer1AfterGettingText3.png){:.enlargeImage}

</hint>

Try this on your own but if you get stuck you can click the Solution button.

## Test Your App again
Congratulations, you have built your first voice driven AI system.  Test it thoroughly to make sure that your Voice Calculator can correctly respond to a variety of different utterances for each operation intended.


# Expand Your App
* The calculator at this point functions a lot like how a beginning foreign language learner may try to function in a foreign country when listening to a native speaker: a few known key words are used to identify the intent of the native speaker and the rest of the other words are completely ignored in high hopes that they are redundant and thus don’t really matter.  For example in the following sentence, all the words in <span style="color:red">red</span> are redundant and can be ignored while the words in <span style="color:green">green</span> are highly relevant in defining the intent of the speaker:

	<span style="color:red">Would you be so kind, oh dear amazing Calculator, to tell me the</span> <span style="color:green">product</span> <span style="color:red">of the most glorious number</span> <span style="color:green">73</span> <span style="color:red">and the supremely wondrous quantity</span> <span style="color:green">51</span> <span style="color:red">?</span>

	* Knowing this limitation of the Voice Calculator, come up with a sentence that will trick it to do a calculation when the intent of the sentence was not a calculation at all.  Test it.
	* Knowing the limitations of the Voice Calculator, come up with a completely legitimate calculation sentence that it will fail to understand. Test it.
	* Can you improve your code to avoid any of the tricky sentences you came up with above?

* Make the calculator take square roots and other more advanced operations you might know.

* Can you try to create a primitive version of Alexa or Siri where the AI will respond to some basic queries like: 
	* What day of the week is it?
	* What is the time?
	* Tell me a joke.
	* What is the weather? (perhaps opens a weather website)
	* What are the top news stories? (perhaps opens a news website)
	* Set up a timer for 30 seconds.




# About Youth Mobile Power 
A lot of us spend all day on our phones, hooked on our favorite apps. We keep typing and swiping, even when we know the risks phones can pose to our attention, privacy, and even our safety.  But the computers in our pockets also create untapped opportunities for young people to learn, connect and transform our communities.

That’s why MIT and YR Media teamed up to launch the Youth Mobile Power series. YR teens produce stories highlighting how young people use their phones in surprising and powerful ways. Meanwhile, the team at MIT is continually enhancing MIT App Inventor to make it possible for users like you to create apps like the ones featured in YR’s reporting.

Essentially: get inspired by the story, get busy making your own app!
 <img src="../images/logos/NSF_4-Color_bitmap_Logo.png" width="75"><img src="../images/logos/MITAppInvlogo1.jpg" width="75"><img src="../images/logos/LOGO_YR_PNG_TRANS.png" width="75">
 
 The YR + MIT collaboration is supported in part by the National Science Foundation. This material is based upon work supported by the National Science Foundation under Grant No. (1906895, 1906636).   Any opinions, findings and conclusions or recommendations expressed in this material are those of the author(s) and do not necessarily reflect the views of the National Science Foundation.

 Check out more apps and interactive news content created by YR <a href="https://yr.media/category/interactive/" target="_blank">here</a>.