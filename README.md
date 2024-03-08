This is the changelog for a SpringBoot web application created initially by WGU and changed by me. All changes are outlined in detail below. This project is being uploaded with permission from WGU for use in a professional portfolio.


Prompt C: Customize the HTML user interface for your customer’s application. The user interface should include the shop 
name, the product names, and the names of the parts.  

    File Edited: mainscreen.html  

        Line Numbers Edited: 13
        Changes Made: Changed title to "Mike's Camera Shop"

        Line Numbers Edited: 18
        Changes Made: Changed generic shop name to "Mike's Camera Shop"

        Line Numbers Edited: 20
        Changes Made: Changed "Parts" to "Lenses, Replacement Buttons, and SD Cards"

        Line Numbers Edited: 52
        Changes Made: Changed "Products" to "Cameras"

Prompt D: Customize the HTML user interface for your customer’s application. The user interface should include the shop 
name, the product names, and the names of the parts.

    File Edited: mainscreen.html  

        Line Numbers Edited: 88 - 89
        Changes Made: Added button to navigate to "about.html"

    File Edited: about.html 

        Line Numbers Edited: 1 - 23
        Changes Made: Created "about.html" and included information about Mike, as well as navigation to "mainscreen.html"

    File Edited: AboutController.java

        Line Numbers Edited: 1 - 19
        Changes Made: Created "AboutController.java" and wired to application

Prompt E: Add a sample inventory appropriate for your chosen store to the application. You should have five parts and 
five products in your sample inventory and should not overwrite existing data in the database.

    File Edited: mainscreen.html  

        Line Numbers Edited: 20 & 52
        Changes Made: Changed "Lenses, Replacement Buttons, and SD Cards" to "Lenses and Replacement Parts"
                      Changed "Cameras" to "Cameras and Accessories"

    File Edited: H2 Database
        
        Changes Made: Added 5 parts and 5 products to H2 Database

Prompt F: Add a “Buy Now” button to your product list. Your “Buy Now” button must meet each of the following parameters:

•   The “Buy Now” button must be next to the buttons that update and delete products.
•   The button should decrement the inventory of that product by one. It should not affect the inventory of any of the 
associated parts.
•   Display a message that indicates the success or failure of a purchase.
    
    File Created: failedpurchase.html
        
        Changes made: Creates a webpage to display when a product could not be purchased due to it being out of stock.
    
    File Created: purchase.html

        Changes made: Shows a confirmation page letting users know they have successfully purchased an item

    File Edited: mainscreen.html 

        Line Numbers Edited: 84
        Changes Made: Addedd "Purchase" button to all Products that calls the "purchaseProduct" function when clicked

    File Edited: MainScreenController.java
        
        Line Numbers Edited: 58-72
        Changes Made: Added purchaseProduct function that is passed a productID via mainscreen.html, retrieves the matching
        entity from DB, verifies if its inventory is > 0, returns an error if it is not, and purchases a product if it is

Prompt G: Modify the parts to track maximum and minimum inventory by doing the following:

•   Add additional fields to the part entity for maximum and minimum inventory.

•   Modify the sample inventory to include the maximum and minimum fields.

•   Add to the InhousePartForm and OutsourcedPartForm forms additional text inputs for the inventory so the user can set the maximum and minimum values.

•   Rename the file the persistent storage is saved to.

•   Modify the code to enforce that the inventory is between or at the minimum and maximum value.


    File Edited: Part.java

        Line Numbers Edited: 31-32
        Changes Made: Addedd minimum and maximum fields to entity

        Line Numbers Edited: 95-110
        Changes Made: Addedd getter/setter methods for minimum and maximum fields

    File Edited: OutsourcesPartForm.html
        
        Line Numbers Edited: 27-31
        Changes Made: Added fields for minimum and maximum values

    File Edited: InhousePartForm.html
        
        Line Numbers Edited: 26-31
        Changes Made: Added fields for minimum and maximum values

    File Edited: AddOutsourcedPartController.java

        Line Numbers Edited: 42-47
        Changes Made: Added logic to determine if minimum and maximum values are within bounds and deny update if they
        are not

    File Edited: AddInhousePartController.java

        Line Numbers Edited: 41-46
        Changes Made: Added logic to determine if minimum and maximum values are within bounds and deny update if they
        are not

Prompt H: Add validation for between or at the maximum and minimum fields. The validation must include the following:

•   Display error messages for low inventory when adding and updating parts if the inventory is less than the minimum number of parts.

•   Display error messages for low inventory when adding and updating products lowers the part inventory below the minimum.

•   Display error messages when adding and updating parts if the inventory is greater than the maximum.

    File Created: MaximumInventoryError.html

      Changes Made: Displays an error message alerting users that inventory is higher than acceptable maximum

    File Created: MinimumInventoryError.html

      Changes Made: Displays an error message alerting users that inventory is lower than acceptable minimum

Prompt I: Add at least two unit tests for the maximum and minimum fields to the PartTest class in the test package.

    File Edited: PartTest.java

        Line Numbers Edited: 152-167
        Changes Made: Added tests for setting minimum and maximum values for inhouse and outsourced parts

Prompt J: Remove the class files for any unused validators in order to clean your code.

    Files Removed: DeletePartValidator
