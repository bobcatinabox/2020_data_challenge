Bobcat In A Box Thanksgiving Data Challenge (for more head to bobcatinabox.com/2020-data-contest)

<b>Data Description</b>

tbl_test_boxes.csv (this is the file you need to submit, each row is one box)
    unboxer_id (unique to each unboxer, use to lookup data accross tables)
    vendor_id (unique to each vendor, use to lookup data accross tables)
    target_bobcat (you need to figure this one out)
    tbl_train_boxes.csv (these boxes are your training data, each row is one box)

unboxer_id
  vendor_id 
  target_bobcat (we are trying to predict the 1s)
  tbl_unboxer_attributes.csv (these features describe each unboxer)

unboxer_id 
  feature_skimask 1-60 (discrete variables)
  feature_beartrap 1-5 (discrete variables that are labels for attributes such as geography and gift/prank status)
  tbl_unboxer_keywords.csv (these are keywords selected by each unboxer)

unboxer_id
  keyword_id (unique to each keyword, use to lookup data accross tables)
  enabled (1 if keyword is selected by unboxer, -1 if keyword isn't selected by unboxer)
  tbl_vendor_keywords.csv (these are keywords used by each vendor)

vendor_id
  keyword_id
  enabled (all 1s)
  
<b>Evaluation</b>

To make a submission please send tbl_test_boxes.csv with your best estimates of target_bobcat, the code you used to generate the result and some documentation of what you did to data@bobcatinabox.com

target_bobcat should be a decimal value between 0 and 1 that reflects your model's confidence in whether or not a box contains a bobcat (0 means you don't think there is any chance of a bobcat, 1 means that you are certain that a box contains a bobcat).

To evalate your submission, we will rank the boxes using your target_bobcat and take a look at how many bobcats there actually were in the predicted top 5% of tbl_test_boxes. The winning submission will be the one that has the largest number of actual bobcats in the 5% of boxes with the highest target_bobcat values in tbl_test_boxes.

To count as a qualifying submission, your predicted top 5% of tbl_test_boxes must contain at least 25% actual bobcats. Accross the whole dataset 12.5% of boxes contain bobcats.

Please do not submit a large number of high and identical target_bobcat values as this may gum up the works when it comes time to evaluate the top 5%.

Hints: As we are only looking at the top 5%, false positives are a larger problem than false negatives. Bobcats are inherently unpredictable creatures. If in cross validation your model is correctly predicting over 45% of the target_bobcat vales then it has overfitted to the training data and you are doing something wrong.

Click below to join our Discord channel and discuss the contest!
https://bobcatinabox.com/discord-channel
