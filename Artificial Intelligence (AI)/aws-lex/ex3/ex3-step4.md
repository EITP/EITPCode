# Step 4: Add the Lambda Function as a Code Hook

In this section, you update the configurations of both the BookCar and BookHotel intents by adding the Lambda function as a code hook for initialization/validation and fulfillment activities. Make sure you choose the $LATEST version of the intents because you can only update the $LATEST version of your Amazon Lex resources.

1. In the Amazon Lex console, choose the **BookTrip** bot. 

1. On the **Editor** tab, choose the **BookHotel** intent. Update the intent configuration as follows:

   1. Make sure the intent version (next to the intent name) is $LATEST. 

   1. Add the Lambda function as an initialization and validation code hook as follows:
      + Choose **Initialization and validation code hook**.
      + Choose your Lambda function from the list.

   1. Add the Lambda function as a fulfillment code hook as follows:
      + In **Fulfillment**, choose **AWS Lambda function**.
      + Choose your Lambda function from the list.

   1. Choose **Save Intent**.

1. On the **Editor** tab, choose the BookCar intent. Follow the preceding step to add your Lambda function as validation and fulfillment code hook.

1. Choose **Build**. The console sends a series of requests to Amazon Lex to save the configurations.

1. Test the bot. Now that you a have a Lambda function performing the initialization, user data validation and fulfillment, you can see the difference in the user interaction.   
![](../images/book-trip-with-lambda-30.png)

1. Continue the conversation and book a car as shown following:  
![](../images/book-trip-with-lambda-40.png)

   When you choose to book a car, the client (console) sends a request to Amazon Lex that includes the session attributes (from the previous conversation, BookHotel). Amazon Lex passes this information to the Lambda function, which then initializes (that is, it prepopulates) some of the BookCar slot data (that is, PickUpDate, ReturnDate, and PickUpCity).
   
**Note**  
This illustrates how session attributes can be used to maintain context across intents. The console client provides the **Clear** link in the test window that a user can use to clear any prior session attributes.

**Video Reference**  
https://www.youtube.com/watch?v=YiFcG5dXxo4

**Next Step**  
[Step 5 (Optional): Capturing and Validating Alphanumeric Identifiers](ex3-step5.md)
