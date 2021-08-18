# Cindy-Visualization-Protocol
Prerequisite

Google Sheet
Google Script

Step 1
Copy and Paste this paragraph of code in Google Script Editor 
OR Open 

https://docs.google.com/spreadsheets/d/1CuMniVt8FHsuK6Ng-2B9WAoA1lDuXJ_7_zqB3G80Ps8/edit#gid=1112563936 

And go to Google Script Editor from this document. You will see the same paragraph of codes already added to the editor. 

Step 2
We are still in the process of identifying more buzzwords and replaceable words to make our sheet more neat. Once you have found those words, sort them side by side with words you are going to replace with. 

In format 
to_replace, replace_with

Step 3
You will need to insert to_replace, replace_with
In this line of code p.s(this is the only line of code you will need to worry about)
replaceInSheet(sheet, ‘to_replace’, ‘replace_with’);

Step 4
Hit ‘Run’

To double check if the changes are successfully made, go back to the active sheet you are on and search for the words you apply the codes on



`function testReplaceInSheet(){
   var sheet = SpreadsheetApp.getActiveSheet()
   replaceInSheet(sheet,'Seal','Neal');
}`
 
`function replaceInSheet(sheet, to_replace, replace_with) {`
 //get the current data range values as an array
 `var values = sheet.getDataRange().getValues();`
 
 //loop over the rows in the array
 `for(var row in values){`
 
   //use Array.map to execute a replace call on each of the cells in the row.
   `var replaced_values = values[row].map(function(original_value){
     return original_value.toString().replace(to_replace,replace_with);
   });`
 
   //replace the original row values with the replaced values
   `values[row] = replaced_values;
 }`
 
 //write the updated values to the sheet
 `sheet.getDataRange().setValues(values);`
}
