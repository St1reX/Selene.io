# Lunar || Selene.io
## 1. Project characteristics
The goal of the Lunar e-commerce project, which sells software and gift cards, is to create an online platform that allows customers easy access to a variety of digital products. By providing an intuitive user interface that allows customers to conveniently purchase software and gift cards online. Additionally, this project is intended to provide appropriate product, order and customer management functionalities for store owners, thus ensuring effective business service.

## 2. System description: 
- **Project modules:**
   * Cart module:
      + Adding products to the cart
      + Removing products from the cart
      + Possibility to edit the number of products in the cart and calculate the new cart value in real time
   * Products module:
      + Displaying products with a gallery of their photos
      + Product filtering
   * Administrator module:
      + User management
      + Product management
      + Product photo management
      + Managing promotional codes
      + Order management
      + Category/subcategory management
   * User module:
      + Adding/removing products to favorites
      + Adding product reviews
      + Edit password
      + Editing your nickname
      + Edit your profile picture
      + Sending a collaboration form
      + Checking order status
   * Login/registration module:
      + Possibility to reset your password
      + Possibility to log in/register using: website form, Google, Facebook, Discord (you need to add clientID and client secret yourself)
      + Sending an email to confirm account registration and password reset
   * Orders module:
      + Invoice generation
      + Sending an mail with an invoice after placing an order
      + Sending an email when there is a change in order status
- **Additional functionalities:**
   * Generating, saving and sending an invoice to the customer after placing an order
   * Possibility to reset your password with reset confirmation via e-mail
   * Possibility to change password from within the user profile
   * Possibility to change your profile photo
   * Possibility to log in/register via Discord
   * Possibility to log in/register via Google
   * Possibility to log in/register via Facebook
   * Sending an activation email when creating a new account
   * Ability to add/remove products to favorites and display favorite products on the user's profile
   * Ability to review the product and display the review on the user's profile
   * Possibility to view another user's profile
   * Possibility to check the order status on the OrderStatus website
   * Possibility to send information about willingness to cooperate via the Collaboration form
   * Possibility to use a discount code on products in the cart
   * Possibility to filter products
   * Possibility to filter all subpages of the admin panel, i.e. products, categories, etc.
   * Possibility to manage users from the administrator panel (modification, addition, deletion)
   * Possibility to manage promotional codes from the administrator panel (modification, adding, deleting)
   * RWD view on all pages except the admin panel
- **User groups:**
  * User not logged in:
    + Ability to browse products on the home page and filter them
    + Ability to view product details and reviews
    + Ability to visit the About Us and Contact pages and send the collaboration form
    + Ability to check the status of your order on the Order Status page
  * Logged in user:
    + Ability to perform the same actions as a non-logged in user
    + Ability to add products to the cart
    + Ability to place orders
    + Ability to post product reviews and add products to favorites
    + Ability to view details of your profile and the profiles of other users
    + Ability to edit your account's password, nickname and profile photo
  * Admin:
    + Possibility to perform the same actions as the logged in user, apart from changing the nickname
    + Access to the administration panel
    + Manageability: products, product photos, categories and subcategories, users, orders, promotional codes from the admin panel
- **Database:**
    ![Database screenshot](https://i.imgur.com/mGnArNg.png)
- **Reports and explanations:**
  * USER table:
    + Connected to the mail_verify table, which contains records about newly created accounts requiring verification and tokens
    + Connected to the favorite_product table which contains information about a given user's favorite products
    + Connected to the product_review table where there is information about product reviews posted by the user
    + Connected to the collaboration table, which contains queries sent by the form regarding collaboration. If they were sent by a logged-in user, they will be associated with that user
    + Connected to the user_adress table, which contains user addresses that go there when placing the first order and are updated with each subsequent order.
    + Connected to the password_reset table where there are records regarding password reset (in case of forgetting, etc.) and tokens necessary for the reset
    + Connected to the cart table to assign a specific cart to a specific user
  * PRODUCT table:
    + Connected to the favorite_product and product_review tables. Explanations about the content of these tables can be found in point USER.
    + Linked to the product_photos table to assign photos to a specific product
    + Connected to the product_categories table (many-to-many relationship) to assign products to specific categories
    + Linked to the cart_product table to identify the product in the cart
  * CART table:
    + Connected to the cart_product table to assign specific records with products and their multitude to specific user carts
    + Connected to the order_ table to assign a specific cart to a specific order
  * CATEGORY/SUBCATEGORY tables:
    + The category table is connected to the subcategory table so that each subcategory is assigned to a specific category, e.g. Adenture to Games.
    + The subcategory table is connected to the product_categories table (many-to-many relationship) so that products can be assigned to specific subcategories (this makes more sense when used in practice, as it         allows for specific filtering, e.g. not by Games alone, but by Adventure Games)
  * Other minor tables:
    + The user_address table is assigned to order_ to include the user's address with the order
    + The order_status table is assigned to order_ so that order statuses can be easily managed
    + The promo_code table is assigned to cart so that discount codes can be easily applied to the contents of users' carts








