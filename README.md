    **This Document for Backend(GraphQl) customization**
##  **Insider Community**

-    The insider community is shown on home page of <https://alike.io/>.
-   **Module**: `Nik_InsiderPageGraphQl`
-   **Resolver**: `Nik\InsiderPageGraphQl\Model\Resolver\InsiderCommunity`
-   In the resolver file return data like id, name,profile_picture etc
    using insiderId.
-   **Admin Menu**: `STORE`->`Configuration`->`CUSTOM`-\>`Insider`-\>`Home Page Configuration`
     set the Insider Community text field. here admin set a coma
     separating **insider's ID** and showed it in insider community.

##  **Explore Cities Nearby**
-   Explore Cities Nearby is shown on <https://alike.io/cities/> page.
-   **Module**: `Nik_Cities`
-   Here `CategoryInterface` in Citycustom query for this block.
-   **Resolver**: `Nik\Cities\Model\Resolver\CityCustom`
-   **Admin Menu**: `Catalog`-\>`Category`-\>`Content`-\>`Explore
     Nearby` Here admin set a coma separated **city's ID** and showed it in
     Explore Cities Nearby.
-   In the resolver file return data name, image, and highlights load by
     Explore Nearby cities id.

##  **BlackFriday Phases**
-   The Black Friday sale is shown on <https://alike.io/black-friday/> page.
-   Black Friday Sale in three phases.
-   `StoreConfig` GraphQl uses BlackFriday reserve price and SKU.
-   `passHotel` and `passProduct` GraphQl use and items Query to retrieve
    data.
-   **Module**: `NaS_Ticket`
-   **Module**: `Nik_Sendinblue`
-   In schema.graphql file sent mutation
    `subscribeToBlackFridayPhase`.
-   Here set the black friday phase and input like `name`,`first_name`, and
    `email`.
-   **Resolver**:
    `Nik\Sendinblue\Model\Resolver\SubscribeToBlackFriday`
-   In resolver get data by \$params and set id by scopConfig.
-   **Admin Menu:** `STORE`->`Configuration`->`CUSTOM`-\>`Sendinblue`-\>`Brevo Lists Settings`
    in set template for BlackFriday.
-   BlackFriday Phase 1 & 2 consists text field for set templates for
    phases. here set the brevo email template ID.

##  **Currency GraphQl**
-   Currency GraphQl use for setup currency in website.
-   **Module**: `Magefan_AutoCurrencySwitcher`
-   **STORE_Configuration:** `GENERAL`-\>`Currency Setup` to set currency
    and configuration on it.
-   **Resolver**:
    `Magefan\AutoCurrencySwitcher\Model\Resolver\Currency`
    
##  **VirtualProduct GraphQl**
-   `New_product` GraphQl call in home page for Best Selling Experiences.
-   **Module**: `Nik_CatalogGraphQl`
-   Here Product interface uses and return data by ID.
-   **Resolver**:`Nik\CatalogGraphQl\Model\Resolver\Product\NewProducts`

##  **PreviewProducts GraphQl**
-   `homepage_stories_products` GraphQl is used for Handcrafted Holiday
    Packages.
-   Handcrafted Holiday Packages are located on home page.
-   **Module**: `Nik_CatalogGraphQl`
-   **Resolver**:`Nik\CatalogGraphQl\Model\Resolver\Product\HomepageStoriesProducts`
     in set page size
-   All products are in set sort order and this sort order field uses
    filter `homepage_stories` product.
    
##  **Cart GraphQl**
-   Cart GraphQl use for
    <https://alike.io/cart> page.
-   `AvailablePaymentMethod` graohql use in cart page.
-   **Module**: `Nik_CheckoutGraphQl`
-   **customInfo** GraphQl also use in cart page.
-   **customInfo** GraphQl set in `CartItemsInterface`.
-   **Resolver:**`Nik\CheckoutGraphQl\Model\Resolver\CustomOptions`
     resolver use for CartItems.
-   **Module**: `Nik_CheckoutGraphQl` module use for CustomInfo GraphQl.
-   **Resolver:** `nik\CheckoutGraphQl\Model\Resolver\OrderCustomOptions`
-   `addHotelXProductToCart` mutation use for after we select hotel
    rooms.
-   **Resolver**:
   `NaS\Travelgatex\Model\Resolver\AddHotelXProductsToCart`
-   `Payment method`, `Shipping method`, `coupon`, etc configure in this
    graphql.

##  **Cities page**
-   In cities, pages are located at
    <https://alike.io/cities/> page.
-   All Cities are one type of category in alike.
-   **Module**: `Nik_Cities`
-   `custom` graphql use for city custom.
-   **Resolver:**
-    `Nik\Cities\Model\Resolver\CityCustom`
-   `Citycustom`, `Explore Nearby`, and `Faq` also use the city page.
-   Also, Top Attractions handcrafted holidays block is used on this
    page.
-   StoriesProducts & ActivitiesProducts GraphQl call from
    `NaS_Widgets` module.
-   CityFaqs `Nik_Faqs` module use.
-   `CityCurrency`, `BestTimeToVisit`, `MonthsWeather` set in category
    interface. `Nik_CatalogGraphQl` module.
-   `get_product` mutation to use retrieve product by input parameter.
-   **Resolver**:`Nik\CatalogGraphQl\Model\Resolver\Booking\RaynaProduct`
-   `getRaynaTickets` is query to using rayna api thru return and book
    ticket and
-   **Resolver**:`Nik\CatalogGraphQl\Model\Resolver\Booking\RaynaTickets`
-   `getRaynaTicketsSlot` using this query book slot by date.
-   **Resolver**:`Nik\CatalogGraphQl\Model\Resolver\Booking\RaynaTicketSlot`

##  **Product Interface**
-   Product Interface used for retrieving data from product and it's
    attribute.
-   <https://alike.io/products>
    age in using product interface to return data.
-   **Module**: `Nik_CatalogGraphQl`
-   In garphql `items` are denoted as one product to return from the
    product interface.
-   `adult_lable` is a custom field to add in the interface. it
    **Resolver**:`Nik\CatalogGraphQl\Model\Resolver\Product\AdultLabel`
-   `api_connected_label returns` the connected name. **Resolver**:
    `Nik\CatalogGraphQl\Model\Resolver\Product\ApiLabel`
     resolver.API connected is one type of attribute to add from the
     admin panel and api_connected_label returns name of attribute.
-   `dynamicAttribute` field to add product interface **Module**:
    `Nik_DynamicAttributes`.
-   **Resolver:**`Nik\DynamicAttributesGraphql\Model\Resolver\Product\DynamicAttributes`
-   `dynamicAttribute` return data in array foam. It is a one type of
    collection of some attribute.
-   `GlobaltixAvailability` query also use in product interface.
-   **Resolver:**`Nik\CatalogGraphQl\Model\Resolver\Product\GlobaltixAvailability`
-   That resolver use to retrieve data. Using globlatixFactory in which
     id is active that return product.
-   `hide_adult`, `hide_child`, `hide_infant` are attributes to set in
     `store`-\>`product attribute`.
-   `include_in_touristors` is a custom attribute to add in product
     interface. **Resolver**:`Nik\\\\CatalogGraphQl\\\\Model\\\\Resolver\\\\Product\\\\IncludedTouristors`
-   `included_trips` attribute to add in product interface and
     **Resolver**:`Nik\CatalogGraphQl\Model\Resolver\Product\IncludedTrips`
-   `kit_avability` add in interface and **Resolver**:
    `Nik\CatalogGraphQl\Model\Resolver\Product\KitAvailability`
     In resolver get data to fetching kit API and return those data to
     come from kit API.
-   `strike_price_value` is set in product interface and **Resolver**:
     `Nik\CatalogGraphQl\Model\Resolver\Product\StrikePrice`.
-   `rayna_city_id`, `rayna_contract_id`, `rayna_country_id`, `rayna_ id`
     thru return city to `city`,`rayna_contract_id`, `rayna_country_id`
     and `rayna_id`attributes.
-   `sort_discription_alike` input parameter to input description when
     create a trip story.
-   `strike_price_value` set in product interface and **Resolver**:
    `Nik\CatalogGraphQl\Model\Resolver\Product\StrikePrice`.
-   `touristor_saver` also add-in product interface and **Resolver**:
     `Nik\CatalogGraphQl\Model\Resolver\Product\TouristorSaver`
     is a.
-   `url_key` is set in touristor_saver query, and **Resolver**:
    `Nik\CatalogGraphQl\Model\Resolver\Product\Tourist`.here
     retrieve url_key from product factory.
-   `ins_city` attribute is set from the admin product attribute and
     config from the `Nik_CatalogGraphQl` module.
-   **Resolver:**`Nik\CatalogGraphQl\Model\Resolver\Product\InsCustomAttributes`
-   `is_liked` also set in product attribute and **Resolver**:
    `Nik\CatalogGraphQl\Model\Resolver\Product\IsLiked`.
-    `page_info` and `total_count` are used in the ProductComment query
     in CatalogGraphQl schema. graphql file.
-   `base_video` use in trip story page and code configuration in
     **Module:** `Nik_CatalaogGaraphQl`
-    **Resolver:**`Nik\CatalogGraphQl\Model\Resolver\Product\BaseVideo`
-   `icons` are set in product attribute and **Resolver**:
    `Nik\CatalogGraphQl\Model\Resolver\Product\HeaderIcons`.
-   `ins_days` is a filter input to add in preview_product query.
-   **Resolver:**`Nik\CatalogGraphQl\Model\Resolver\Product\PreviewProducts`
     to return data from collectionFactory.
-   `Ins_highlights` is added in product interface and **Resolver**:
     `Nik\CatalogGraphQl\Model\Resolver\Product\InsHighlights`.
-   **Admin Menu:** `STORE`->`Configuration`->`CONTENT`-\>`Cities`-\>`City Highlights Listing`
-   `insider_data` set in the product interface and **Resolver**:
    `Nik\CatalogGraphQl\Model\Resolver\Product\ProductInsider`.here
     fetch data from insiderFactory.
-   `itinerary` is a added in product graphql and **Resolver**:
     `Nik\CatalogGraphQl\Model\Resolver\Product\Itinerary`.
-   `product_like` is a product interface and
-   **Resolver:**`Nik\CatalogGraphQl\Model\Resolver\Product\ProductLikeAttribute`
-   `story_type` is product interface parameter and **Resolver**:
    `Nik\CatalogGraphQl\Model\Resolver\Product\ProductStoryType`.
-   `product_comment` is a product interface used and **Resolver**:
     `Nik\CatalogGraphQl\Model\Resolver\Product\ProductComment`.
-   `getProduct` add-in product interface and **Resolver**:
    `Nik\CatalogGraphQl\Model\Resolver\Booking\RaynaProduct`.in
     resolver return data using kit API.
-   `insiderTickets` mutation added in the product interface, when we
     select trip story at that time use this mutation and **Resolver**:
    `Nik\CatalogGraphQl\Model\Resolver\Booking\Insider`.
-   Also, `itineraryPrice` mutation add and **Resolver**:
    `Nik\CatalogGraphQl\Model\Resolver\Booking\ItineraryPrice`.
    
##  **Travel Passes Page**
-   Travell passes are coming from
    <https://alike.io/travel-passes?utm_source=site&utm_medium=menu-desktop&utm_campaign=menu> page.
-   On this page use the categories interface and return data.
-   **Module**: `Nik_CataloggraphQl`
-   **Admin Menu:** `STORE`-\>`Attribute`-\>`Product`
-   **Resolver**:`Nik\CatalogGraphQl\Model\Resolver\Esim`. In
    this resolver set page size add a filter as an attribute and
    return data.
-   If we can click any passes move to <https://alike.io/products/the-london-passr> page.
-   Also, this page uses a product interface.
-   Musement API through select date for ticket and book ticket.
-   **Resolver:**`Nik\CatalogGraphQl\Model\Resolver\Booking\MusementTickets`
-   **Admin Menu:** `STORE`->`Configuration`->`NAS`-\>`Musement API` path.
-   Musement activity configuration in **Resolver**:
    `app/code/Nik/CatalogGraphQl/etc/schema.graphqls`**.**
-   **Resolver:**`Nik\CatalogGraphQl\Model\Resolver\Booking\MusementActivity`
-   This code fetches Musement activity data based on GraphQl input
    parameters and handles exceptions during the process and
    `booking_type` and `order_box` a input parameters of musement
    activity.
-   Musement tickets configuration in **Module**:
    `Nik_CatalogGraphQl`.
-   **Resolver**:`Nik\CatalogGraphQl\Model\Resolver\Booking\MusementTickets`
-   In Musement tickets, resolver fetches Musement ticket data,
    retrieves associated product information, processes the data, and
    adjusts prices based on certain parameters.

##  **eSIMs Page**
-   <https://alike.io/esims?utm_source=site&utm_medium=menu-desktop&utm_campaign=menu> page
    URL for eSIMs page.
-   Here Category is used as a filter. And call `CategoryInterface` for a
    category.
-   **Module:** `Nik_CataloggraphQl`
-   **Resolver**: `Nik\CatalogGraphQl\Model\Resolver\Esim`
-   Set `E SIM` attribute set and use in resolver to filter products for
    eSIMs.
    
##  **Winter Sale**
-   The Winter Sale page URL is
    <https://alike.io/winter-sale?utm_source=site&utm_medium=menu-desktop&utm_campaign=menu>.
-   In winter sales use product interface to retrieve product.
-   Here winter sale is only for Dubai.
-   **Module**: `NaS_Ticket`
-   Here is another GraphQl use for Attraction Bundle
    `passProduct`.
-   `passProduct` query located at `NaS_Ticket` module.
-   **Resolver:** `NaS\Ticket\Model\Resolver\PassProducts`
-   `passHotel` GraphQl used for Hotel.
-   **Resolver:** `NaS\Ticket\Model\Resolver\PassHotel`
-   This resolver uses collectionFacteory to retrieve hotel and return
    data.

## **Cart Page**
-   When we add a product to the cart then reach
    <https://uat.alike.host/cart> page.
-   On this page `addProductToCart` GraphQl call.
-   **Module**: `Nik_CataloggraphQl`
-   **Resolver**: `Nik\CatalogGraphQl\Model\Resolver\Booking\AddProductToCart`
-   In this resolver get items in the cart and configure it.
-   Then we can continue to the next step `setShippingAddressesOnCart`
    GraphQl call.
-   After the next step add our details between contact detail and
    payment option step to call `abandonedCartCapture` GraphQl call.
-   `abandonedCartCapture` GraphQl at `Nik_AbandonedCartCapture` module.
-   **Resolver:** `Nik\AbandonedGraphQl\Model\Resolver\AbandonedCartCapture`
-   **Admin Menu:** `REPORTING`-\>`Anamdoned`-\>`Reports`
-   Abandoned email configuration on **Admin Menu**:
    `STORE`->`Configuration`->`CUSTOM`-\>`Abandoned`.
    
##  **Signup/Signin Page**
-   Signin page URL is
    <https://app.alike.io/#/signin>.
-   `amSocialLoginButtonConfig` GraphQl used through work signup/sign-in.
-   **Module**: `Amasty_SocialLoginGraphQl`
-   **Resolver**:`Amasty\SocialLoginGraphQl\Model\Resolver\SocialButtons`
-   In resolver (**SocialButtons**) that retrieves information about
    enabled social login buttons using the **SocialData** model from
    the Amasty Social Login extension for Magento 2.
-   Then user creates a successful after-call createCustomerv2 GraphQl
-   **Module**: `Nik_Cities` used for creating customers.
-   **Resolver:** `Nik\Cities\Model\Resolver\Insider\CreateCustomer`
-   <https://app.alike.host/#/account/general> after sign-in as a user reach this page.
-   <https://app.alike.host/#/my-trips/my-bookings/upcoming-order> on this page, the `CustomerOrder` graphql call
-   **Module**: `Nik_SalesGraphQl`
-   **Resolver:**`Magento\SalesGraphQl\Model\Resolver\CustomerOrders`
-   In this resolver filter and get data using ExtensionAttribute.

##  **Become Insider** 
-   In the customer login page, we create also insider account.
-   <https://app.alike.host/#/my-studio/dashboard>
    is a become insider page URL.
-   In this page `BecomeInsider` GraphQl call.
-   **Module**: `Nik_Cities`
-   **Resolver:**`Nik\Cities\Model\Resolver\Insider\BecomeInsider`
-   `MyDeshboard` GraphQl is used for insider's data we can see on the
    dashboard page.
-   **Resolver:**`Nik\InsidersDashboardGraphQl\Model\Resolver\MyDashboardResolver`
-   Get data using insiderFactory.
-   **Admin Menu:** `INSIDERS` section for customization insider.
-   `MyStudioAccount` garphql is used for customizing accounts.
-   **Module**: `Nik_InsidersConfigGraphQl`
-   **Resolver:**`Nik\InsidersConfigGraphQl\Model\Resolver\MyStudioAccountResolver`
-   **Admin Menu:** `INSIDERS`-\>`Profile`-\>`Manage Insiders` section
    configure.
-   `MyTripData` GraphQl is used for listening trip stories. Is located
    `Nik_InsidersDashboardgraphQL` module.
-   `Wallet` GraphQl for account wallet.
-   **Module**: `Nik_InsidersDashboardgraphQL`
-   **Resolver:** `Nik\Cities\Model\Resolver\Wallets`

##  **Hotels & Stays Page**
-   `SearchX` GraphQl is use
    <https://uat.alike.host/hotels> page in the search section.
-   **Module**: `NaS_Travelgatex`
-   Here `SearchX` GraphQl is used for search and **Resolver**:
    `NaS\Travelgatex\Model\Resolver\Search`.
-   **Resolver:** `NaS\Travelgatex\Model\Resolver\SearchList`
-   `map` & `pagination` use in `Hotel` query. Here **Resolver**:
    `NaS\Hotelbeds\Model\Resolver\Hotels`.
-   **Admin Menu**: `STORE`->`Configuration`->`NaS`-\>`HotelBedsApi` in set configuration.
-   `quoteX` graphql use in when we select a hotel room at that time
     use.in code configuration set `quoteX` query and **Resolver**:
     `NaS\Travelgatex\Model\Resolver\Quote`.
-   In `quoteX` add `hotelX` parameter.

## **Product Comment GraphQl**
-   `Product Comment` GraphQl in the particular product page.
-   **Module**: `Nik_CatalogGraphQl`
-   **Resolver:**`Nik\CatalogGraphQl\Model\Resolver\Product\ProductComment`

## **Insider Account Graphql**
-   `InsiderAccount` GraphQl use in particular insider's page.
-   **Module**: `Nik_insiderPageGraphQl`
-   **Resolver:**`Nik\InsiderPageGraphQl\Model\Resolver\InsiderPage`
-   Following graphql configuration in `Nik_Cities` module.
-   **Resolver:** `Nik\Cities\Model\Resolver\Following`
-   returns the result with additional details like profile pictures and
    nicknames. The actual logic for fetching followings is likely
    implemented in the `getFollowings` method of the
    `NaS\SocialAddon\Model\ResourceModel\Follow\CollectionFactory`
    class.
-   `categoryImageId` configuration in the `Nik_CatalogGraphQ` module.
-   **Resolver:**`Nik\CatalogGraphQl\Model\Resolver\Story\CategoryImageIdData`
-   Mytrips configuration in `Nik_InsidersDashboardGraphQl` module.
-   **Resolver:**`Nik\InsidersDashboardGraphQl\Model\Resolver\MyTripsResolver`
-   In resolver for fetching data about trips. It includes methods to
     handle authorization, retrieve insider and product information,
    and build a response containing information about top trips with
    pagination details. The resolver also includes methods to handle
    `image URLs`, `including placeholders`.

## **CategoryInterface**
-   `CategoryInterface` returns data by items.
-   `esim_product` configuration in `Nik_CatalogGraphQl` module.
-   **Resolver:** `Nik\CatalogGraphQl\Model\Resolver\Esim`
-   In resolver (Esim) that retrieves data about eSIM products based on
    various filters. The resolver constructs a product collection,
    applies filters, and returns relevant information in the output
    arrayTop_travelpass_products configuration in the
    `Nik_CatalogGraphQl` module.
-   **Resolver:**`Nik\CatalogGraphQl\Model\Resolver\Travelpass`
-   resolver `Travelpass` that retrieves data about top-rated travel
    passes based on various filters. The resolver constructs a product
    collection, applies filters, and returns relevant information in
    the output array.
    
## **Brevo Lists Customer Group Settings**
-   Admin Menu: `STORE`->`Configuration`->`CUSTOM`->`Sendinblue` here Three fieldset.
-   In `General` fieldset enable/disable the configuration set.
-   `Brevo Lists Customer Group Settings` fieldset in a defined List of some area. We have here given a droup-down for list configuration.
-   `Brevo Lists Template Settings` fieldset in given all types of email configuration.
-   Like signup, email configuration gives a drop-down for selecting brevo email template.
-   If we don’t select a template that time use Magento default template.
-   Here all brevo template shows in a droup-down and select a template for use.

## **Trip Planer**
-  `Trip Planner` is a one the new prodcut we add in Magento 2.
-  Trip Planner is a almost same as bundle product.
-  In trip planner create your trip road map for future trip.
-  In trip planner add visa,hotels,airport transfer and sim for trip.
-  <https://app.alike.host/#/my-trips/trip-planner> here create trip roadmap.
-  In trip planner here provide for type of view provide for trip `Timeline`, `Calendar`, `Map`, and `Summary`.
-  Trip planners can be shared with other people. but need admin login access for any customization.
-  How to create a new product type in magento like trip planner.
   -   Step 1: Generate registration.php file
        - Setup the Nik\TripPlanner\registration.php file
        - Generate the Nik\TripPlanner\etc\module.xml
        - Next, the creation of the `etc/product_types.xml` file is necessary to determine the model of the new product type.
        - Name: the name you need to set for the new product type
        - Label: the label which is visible in the Magento backend
        - Model instance: endorse the product type’s attributes
        - Price Model: endorse the charge of the new product type
   -   Step 2: Add the code NewProductType model
        - Enter the code below: Nik\TripPlanner\Model\Product\Type\NewProductType model, that should be based on Magento\Catalog\Model\Product\Type\AbstractType.
        - After that, it is possible to rewrite some functions and implement some changes you want there.
   -   Step 3: Add the Price model
        - Enter Nik\TripPlanner\Model\Product\Price model, which should be based on the Magento\Catalog\Model\Product\Type\Price.
        - Besides, you can also set the new product type as versatile type with some custom functions after extending the Magento\Catalog\Model\Product\Type\Price class
   -   Step 4: Publish the new Magento 2 Product type
        - This is the step allowing you to check the result in the Magento 2 Administrator when completing the above steps. The New Product type will display as the old types (Simple or Configurable Product).
-  `hotel_activity_search` GraphQl used for serval hotel.
-  **Module**: `Nik_CatalogGraphQl`
-  **Resolver**: `Nik\CatalogGraphQl\Model\Resolver\Story\HotelSerachData`
-  `wishlist_v2` GraphQl used for add products in Wishlist. When we plane a trip at time use wishlist to add serval products to the trip.
-  **Module**: `WishlistGraphQl`
-  **Resolver**: `Magento\WishlistGraphQl\Model\Resolver\WishlistById`
-  `CreateTripPlanner` GraphQl use for create trip plane using insider id.trip planner is a almost same as a create trip.
-  **Module**: `Nik_TripPlanner`
-  **Resolver**: `Nik\TripPlanner\Model\Resolver\CreateTripPlanner`



