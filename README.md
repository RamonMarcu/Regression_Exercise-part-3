# Regression
Testing for regression in an application (Exercise)

Regression
The new “clear order” button feature has been implemented to satisfy the new test.

When adding a new feature to your product, it’s possible that something will break. If that break occurs within a feature developed earlier, it is called regression. When functionality previously developed and tested stops working, you may say the functionality regressed.

Running an automated test suite is fast and repeatable, which means you can run tests after every change to confirm that old features still work. If they have regressed, the test output should notify you.

Instructions

1.Code to implement the new “clear order” feature has been added. Start the app and manually test the new and old button features:

Click “Clear”. Expect the order to be empty.
Enter an order and click “Place Order”. Expect the order to be populated with your selections. Do both buttons behave as expected?
When you’re done, check work.

Checkpoint 2 Passed


2.Stop the app by pressing CTRL + C (the control button and C key at the same time), then run the test suite.

You can scroll up to see that the new feature test (“to clear an order”) is passing and the old tests are failing. You found a regression!

When you’re done, check work.

Checkpoint 3 Passed


3.Here’s the bug: The “clear” button is using /place-order instead of /clear-order, making both buttons clear the order!

Fix the regression, step 1: In views/index.handlebars around line 117, find the form

<form action="/place-order" method="post">
and replace it with

<form action="/clear-order" method="post">
Click Check Work when you’ve replaced the code.

Checkpoint 4 Passed

4.Fix the regression, step 2: In routes/index.js around line 13, replace the first instance of

router.post('/place-order', async (req, res) => {
with

router.post('/clear-order', async (req, res) => {
Click Check Work when you’ve replaced the code.

Checkpoint 5 Passed

5.Run the test suite again to confirm the fix works as expected.

If you don’t see 7 passing tests, double check that clear order is on the right line in each file!

When you’re done, check work.

Source of exercise: Codecademy Pro
