# <a name="_rc6r9vsc82ga"></a>Alike documentation
## <a name="_1dqnhyeyex"></a>   **1)  Insider Community:**
- The insider community is shown on home page of alike.io.
- Insider community code configuration in **App/Code/Nik/InsiderPageGraphQl.**
- Here etc/schema.graphqls file in set insider community block.insiderCommunity It is a Query, and **Nik\\InsiderPageGraphQl\\Model\\Resolver\\InsiderCommunity** is a resolver.
- In the resolver file return data like id, name,profile\_picture etc using insiderId.
- In the admin panel **STORE->Configuration->CUSTOM->Insider->Home Page Configuration** set the Insider Community text field. here admin set a coma separating insider’s ID and showed it in insider community.



## <a name="_co22t2bxuuho"></a> 2) **Explore Cities Nearby**
- ## <a name="_aqi9n45e0yox"></a>Explore Cities Nearby is shown on <https://alike.io/cities/> page.
- Explore cities nearby code configuration in **app/code/Nik/Cities/**etc/schema.graphqls.
- Here CategoryInterface in Citycustom query for this block.
- ` `**Nik\\Cities\\Model\\Resolver\\CityCustom** is the resolver for city custom.
- Admin panel in **Catalog->Category->Content->Explore Nearby** Here admin set a coma separated city’s ID and showed it in Explore Cities Nearby.
- In the resolver file return data name, image, and highlights load by Explore Nearby cities id.


## <a name="_d3e7c57cdmi"></a>  **3) BlackFriday phse1**
- The Black Friday sale is shown on <https://alike.io/black-friday> page.
- Black Friday Sale in three phases.
- StoreConfig GraphQl uses BlackFriday reserve price and SKU.
- passHotel and passProduct GraphQl use and items Query to retrieve data.
- StoreConfig GraphQl is located at the **app/code/NaS/Ticket** module. 
- We are code configured in **app/code/Nik/Sendinblue/etc/schema.graphqls.**
- In schema.graphql file sent mutation **subscribeToBlackFridayPhase**.
- Here set the black friday phase and input like name,first\_name, and email.
- **\\Nik\\Sendinblue\\Model\\Resolver\\SubscribeToBlackFriday** is a resolver file for BlackFriday.
- In resolver get data by $params and set id by scopConfig.
- Admin panel in STORE->Configuration->CUSTOM->Sendinblue->Brevo Lists Settings in set template for BlackFriday.
- BlackFriday Phase 1&2 consists text field for set templates for phases. here set the brevo email template ID.


## <a name="_j0onkyuj3kk1"></a>    4) **Currency GraphQL**
- Currency GraphQL use for setup currency in website.
- Currency GraphQl is located at **app/code/Magefan/AutoCurrencySwitcher.**
- **STORE->Congiguration->GENERAL->Currency Setup** to set currency and configuration on it.
- **\\Magefan\\AutoCurrencySwitcher\\Model\\Resolver\\Currency** resolver use for currency.

## <a name="_h6vb3q50v9di"></a>   **5) VirtualProduct GraphQL**
- New\_product GraphQL call in home page for Best Selling Experiences.
- new\_producy GraphQL config in **app/code/Nik/CatalogGraphQl**.
- Here Product interface uses and return data by ID.
- **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\NewProducts** resolver for return data.

## <a name="_a7ch9e3i3npn"></a>   **6) PreviewProducts GraphQL**
- homepage\_stories\_products GraphQL is used for Handcrafted Holiday Packages.
- Handcrafted Holiday Packages are located on home page.
- Thair are **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\HomepageStoriesProducts** resolver in set page size.
- There are all products in set sort order and this sort order field uses filter homepage\_stories product. 


## <a name="_88fegzvmnpti"></a>   **7) Cart GraphQL**
- Cart GraphQL use for <https://alike.io/cart>  page.
- AvailablePaymentMethod grapgQl use in cart page.
- This graphQl located at **app/code/Nik/CheckoutGraphQl** module.
- **customInfo** GraphQl also use in cart page.
- **customInfo** GraphQl set in OrderInterface,and CartItemsInterface.**Nik\\CheckoutGraphQl\\Model\\Resolver\\OrderCustomOptions** resolver use for orderintrface and **Nik\\CheckoutGraphQl\\Model\\Resolver\\CustomOptions** resolver use for CartItemsI.
- In **app/code/Nik/CheckoutGraphQl** module use for CustomInfo GraphQl.
- **Nik\\CheckoutGraphQl\\Model\\Resolver\\OrderCustomOptions** resolver is used to retrieve data.
- **addHotelXProductToCart** mutation use for after we select hotel rooms. **NaS\\Travelgatex\\Model\\Resolver\\AddHotelXProductsToCart** it is a resolver use. 
- Payment method, Shipping method, coupon, etc configure in this graphql.


## <a name="_uz8oj5bqtmap"></a>   **8)Cities page**
- In cities, pages are located at <https://alike.io/cities/>.
- All Cities are one type of category in alike.
- In code configuration **app/code/Nik/Cities** use.
- **custom** graphql use for city custom.
- It is located at **app/code/Nik/Cities** vendor.**Nik\\Cities\\Model\\Resolver\\CityCustom** resolver use to return data.
- Citycustom, Explore Nearby, and Faq also use the city page.
- Also, Top Attractions handcrafted holidays block is used on this page.
- StoriesProducts & ActivitiesProducts GraphQL call from **app/code/NaS/Widgets** module.
- CityFaqs is located in the **app/code/Nik/Faqs** module.
- CityCurrency, BestTimeToVisit, MonthsWeather set in category interface. **app/code/Nik/CataloggraphQl** module.
- **get\_peoduct** mutation to use retrieve product by input parameter.**Nik\\CatalogGraphQl\\Model\\Resolver\\Booking\\RaynaProduct** that is a resolver use.
- **getRaynaTickets** is query to using rayna api thru return and book ticket and **Nik\\CatalogGraphQl\\Model\\Resolver\\Booking\\RaynaTickets** is a resolver to use.
- **getRaynaTicketsSlot** using this query book slot by date.**Nik\\CatalogGraphQl\\Model\\Resolver\\Booking\\RaynaTicketSlot** it is a resolver using rayna api key to fetch and book ticket.

## <a name="_j3iiu082kk5t"></a>    **9) Product Interface**
- Product Interface used for retrieving data from product and it’s attribute.
- <https://alike.io/products> page in using  product interface to return data.
- It’s located at **app/code/Nik/CataloggraphQl** module.
- In garphql “items” denoted as a one product to return from product interface.
- **adult\_lable** is custom field to add in interface.it resolver is **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\AdultLabel.**
- **api\_connected\_label**  is return api connected name.and it is use 	**Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\ApiLabel** resolver.api connected is a one type of attribute to add from admin panel and api\_connected\_label return name of attribute.
- **dynamicAttribute** field to add product interface **app/code/Nik/DynamicAttributes** module.
- **\\Nik\\DynamicAttributesGraphql\\Model\\Resolver\\Product\\DynamicAttributes** resolver use to return data.
- **dynamicAttribute** return data in array foam. It is a one type of collection of some attribute.
- **GlobaltixAvailability** query also use in product interface.
- **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\GlobaltixAvailability**
- That resolver use to retrieve data. Using globlatixFactory in which id is active that return product.
- **hide\_adult, hide\_child, hide\_infant** are attributes to set in store->product attribute.
- ` `**include\_in\_touristors**  is a custom attribute to add in product interface.here **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\IncludedTouristors** resolver use.
- **included\_trips** attribute** to** add in product interface and **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\IncludedTrips** is a resolver use.in resolver file fetch data from product attribute.
- **kit\_avability** add in interface and **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\KitAvailability** resolver use. In resolver get data to fetching kit API and return those data to come from kit API.
- **strike\_price\_value**  is set in product interface and Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\StrikePrice is a resolver.
- **rayna\_city\_id, rayna\_contract\_id, rayna\_country\_id, rayna\_ id** thru return city to ‘city’,’rayna\_contract\_id’, ‘rayna\_country\_id’ and ‘rayna\_id’attributes.
- **sort\_discription\_alike** input parameter to input description when create a trip story.
- **strike\_price\_value** set in product interface and **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\StrikePrice** is a resolver to use.
- **touristor\_saver** also add-in product interface and **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\TouristorSaver** is a resolver.it return data from tourister.
- **url\_key** is set in touristor\_saver query, and 	**Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\Tourist** use this resolver.here retrieve url\_key from product factory.    
- **ins\_city** attribute is set from admin product attribute and config from **app/code/Nik/CatalogGraphQl** module.**Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\InsCustomAttributes** resolver to use. 
- **is\_liked** also set in product attribute and **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\IsLiked** is a resolver to use.** 
- **page\_info and total\_count** is use in ProductComment query in cataloggraphql schema.graphql file.
- **base\_vedio** use in trip story page and code configuration in catalaoggaraphql schema.graphql file.**Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\BaseVideo** it is a resolver use for base\_vedio query.
- **icons** is set in product attribute and **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\HeaderIcons** resolver to use get icon.
- **ins\_days** is a filter input to add in preview\_product query.**Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\PreviewProducts** in this resolver to return data from collectionFactory.
- **Ins\_highlights** is add in product interface and **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\InsHighlights** resolver use to return highlights.
- Highlights is from admin panel CONTENT->Cities->City Highlights Listing.
- **insider\_data** set in product interface and **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\ProductInsider** it is a resolver use.here fetch data from insiderFactory.
- **itinerary** is a added in product graphql and **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\Itinerary** that is a resolver.
- **product\_like** is a product interface and **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\ProductLikeAttribute** it’s a resolver use.
- **story\_type** is product interface parameter and **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\ProductStoryType** is a resolver. 
- **product\_comment** is a product interface use and **Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\ProductComment** it’s a resolver.
- **getProduct** add in product interface and **Nik\\CatalogGraphQl\\Model\\Resolver\\Booking\\RaynaProduct** is a resolver to use.in resolver return data using kit API.
- **insiderTickets** mutation add in product interface, when we select trip story at that time use this mutation and **Nik\\CatalogGraphQl\\Model\\Resolver\\Booking\\InsiderTi** this resolver file use for retrieve the data.
- Also **itineraryPrice** mutation add and **Nik\\CatalogGraphQl\\Model\\Resolver\\Booking\\ItineraryPrice** this resolver use.

## <a name="_gws9ys9wfr0"></a>     **10)Travel Passes Page**
- ` `Travell passes are comes from  <https://alike.io/travel-passes?utm_source=site&utm_medium=menu-desktop&utm_campaign=menu>.
- In this page use categories interface and return data.
- Category interface is located at **app/code/Nik/CataloggraphQl.**
- Travel passes as a product attribute to add in admin STORE->Attribute->Product.
- **Nik\\CatalogGraphQl\\Model\\Resolver\\Esim** is a resolver to set and get data.in this resolver set page size and add filter as a attribute and return data.

`     `**→** If we can click any passes so move to                             <https://alike.io/products/the-london-passr> page.

- Also, this page uses a product interface.
- Musement api thru select date for ticket and book ticket.
- **Nik\\CatalogGraphQl\\Model\\Resolver\\Booking\\MusementTickets** is resolver to fetch live ticket data.
- Musement Api configuration in Admin **STORE->Configuration->NAS->Musement** API path. 
- Musement activity configuration in **app/code/Nik/CatalogGraphQl/etc/schema.graphqls.**
- **Nik\\CatalogGraphQl\\Model\\Resolver\\Booking\\MusementActivity** is musement activity resolver.
- In this code fetches Musement activity data based on GraphQL input parameters and handles exceptions during the process and booking\_type and order\_box is a input parameters of musement activity.
- Musement tickets configuration in **app/code/Nik/CatalogGraphQl/etc/schema.graphqls.**
- **Nik\\CatalogGraphQl\\Model\\Resolver\\Booking\\MusementTickets** is resolver of musement ticket.
- In musement tickets resolver fetches Musement ticket data, retrieves associated product information, processes the data, adjusts prices based on certain parameters.


## <a name="_3fg65a6doebe"></a>   **11) eSIMs Page**
- <https://alike.io/esims?utm_source=site&utm_medium=menu-desktop&utm_campaign=menu> url for eSIMs page.
- Here Category use as a filter. And call category interface for category.
- Also, Product as an eSIMs and use ProductInterface are located in **app/code/Nik/CataloggraphQl.** 
- For eSIMs product use **Nik\\CatalogGraphQl\\Model\\Resolver\\Esim** resolver.
- Set E SIM attribute set and use in resolver to filter products for eSIMs.


## <a name="_i913qndxs6t2"></a>    **12) Winter Sale**
- The Winter Sale page URL is <https://alike.io/winter-sale?utm_source=site&utm_medium=menu-desktop&utm_campaign=menu>.
- In winter sale use product interface to retrieve product.
- Here winter sale is only for Dubai.
- storeConfig GraphQl use in wintersale and it’s located at **app/code/NaS/Ticket** module.
- Here is another GraphQL use for Attraction Bundle passProduct.
- passProduct query located at **app/code/NaS/Ticket** module.
- **NaS\\Ticket\\Model\\Resolver\\PassProducts** resolver file to use.
- passHotel GraphQL used for Hotel.
- **NaS\\Ticket\\Model\\Resolver\\PassHotel** resolver to use return hotel data.
- In this resolver using collectionfacteory to retrieve hotel and return data.

## <a name="_bmypvfcf5q62"></a>**13) Cart Page**
- When we add product to cart then reach <https://uat.alike.host/cart> page.
- In this page addProductToCart GraphQL call.
- This GraphQL use in **app/code/Nik/CataloggraphQl** module.
- **Nik\\CatalogGraphQl\\Model\\Resolver\\Booking\\AddProductToCart** resolver use for this GraphQL.
- In this resolver get items in cart and configuration on it.
- Then we can continue to next step setShippingAddressesOnCart GraphQL call. 
- After the next step add our details between contact detail and payment option step to call abandonedCartCapture GraphQL call.
- abandonedCartCapture GraphQL at **app/code/Nik/AbandonedCartCapture** module.
- **Nik\\AbandonedGraphQl\\Model\\Resolver\\AbandonedCartCapture** resolver use.
- Abandoned report configuration in Admin panel REPORTING->Anamdoned->Reports.
- Abandoned email configuration on STORE->Configuration->CUSTOM->Abandoned in Admin panel.



## <a name="_b4am6q73tlr6"></a>       **14) Signup/Signin Page**
- ` `Signin page URL is <https://app.alike.io/#/signin>.
- amSocialLoginButtonConfig GraphQL used through work signup/sign-in.
- amSocialLoginButtonConfig GraphQL is located at **app/code/Amasty/SocialLoginGraphQl module.**
- **Amasty\\SocialLoginGraphQl\\Model\\Resolver\\SocialButtons** is resolver of amSocialLoginButtonConfig.
- In resolver (**SocialButtons**) that retrieves information about enabled social login buttons using the **SocialData** model from the Amasty Social Login extension for Magento 2.
- Then user creates a successfully after-call createCustomerv2 GraphQL
- In **app/code/Nik/Cities** module use for create customer.
- **\\Nik\\Cities\\Model\\Resolver\\Insider\\CreateCustomer** resolver used for creating customer.
- <https://app.alike.host/#/account/general> after signin as a user reach this page.
- <https://app.alike.host/#/my-trips/my-bookings/upcoming-order> in this page customer order graphql call 
- Customer graphql is located at **app/code/Nik/SalesGraphQL** module.
- **Magento\\SalesGraphQl\\Model\\Resolver\\CustomerOrders** resolver use for customer order.
- In this resolver filter and get data using ExtensionAttribute.


## <a name="_n2tm5aq07lt5"></a>  **15) Become Insider** 
- In the customer login page, we create also insider account.
- <https://app.alike.host/#/my-studio/dashboard> is a become insider page URL.
- In this page BecomeInsider GraphQL call.
- BecomeInsider GraphQL is located at **app/code/Nik/Cities** module.
- **\\Nik\\Cities\\Model\\Resolver\\Insider\\BecomeInsider** in a resolver for create insider account.
- MyDeshboard GraphQL is use for insider’s data we can see in dashboard page.
- **Nik\\InsidersDashboardGraphQl\\Model\\Resolver\\MyDashboardResolver** resolver use for this query.
- Get data using insiderFactory.
- In Admin panel **INSIDERS** section for customization insider.
- MyStudioAccount garphql use for customize account.
- MyStudioAccount garphql located at **app/code/Nik/InsidersConfigGraphQL**.
- **Nik\\InsidersConfigGraphQl\\Model\\Resolver\\MyStudioAccountResolver** resolver use for garaphql.
- In admin panel, **INSIDERS->Profile->Manage Insiders** section configure.
- MyTripData GraphQL use for listening trip story. Is located at **app/code/Nik/InsidersDashboardgraphQL** module.
- Wallet GraphQL for account wallet.
- Wallet GraphQl is located at **app/code/Nik/InsidersDashboardgraphQL** module.
- And **Nik\\Cities\\Model\\Resolver\\Wallets** is a resolver.

## <a name="_y4kuao7pix1x"></a>   **16) Hotels & Stays Page**
- SearchX GraphQL is use <https://uat.alike.host/hotels> page in search section.
- SearchX GarphQL is located at **app/code/NaS/Travelgatex** module.
- Here SearchX GraphQL use for search and **NaS\\Travelgatex\\Model\\Resolver\\Search** is resolver.
- **NaS\\Travelgatex\\Model\\Resolver\\SearchList** resolver use for SearchListX.
- map & pagination use in **Hotel** query. Here **NaS\\Hotelbeds\\Model\\Resolver\\Hotels** is a resolver use.in admin panel data set in STORE->Configuration->NaS->HotelBedsApi in set configuration.
- **quoteX** graphql use in when we select hotel room at that time use.in code configuration set quoteX query and **NaS\\Travelgatex\\Model\\Resolver\\Quote** it’s resolver to use.
- In quoteX add hotelX parameter. 

**17) Product Comment GraphQL**

- Product Comment GraphQL in particular product page.
- ProductComment located at **app/code/Nik/CatalogGraphQl** module.
- Nik\\CatalogGraphQl\\Model\\Resolver\\Product\\ProductComment resolver file to use in this graphql.

**18) Insider Account Graphql**

- InsiderAccount GraphQl use in particular insider’s page.
- InsiderAccount GraphQl configure in **app/code/Nik/insiderPageGraphQl** module.
- **Nik\\InsiderPageGraphQl\\Model\\Resolver\\InsiderPage** resolver use in InsiderAccount graphql.
- Following graphql configuration in **code/Nik/Cities/etc/schema.graphqls.**
- **Nik\\Cities\\Model\\Resolver\\Following** is a customer following resolver.
- returns the result with additional details like profile pictures and nicknames. The actual logic for fetching followings is likely implemented in the **getFollowings** method of the **NaS\SocialAddon\Model\ResourceModel\Follow\CollectionFactory** class.

- Wallets graphql configuration in **app/code/Nik/Cities/etc/schema.graphqls.**
- **Nik\\Cities\\Model\\Resolver\\Wallets** is wallets resolver.
- resolver for retrieving information about a user's wallet transactions and It includes logic for handling authorization, loading credit information, filtering and sorting transactions, and providing pagination details.
- categoryimageid configuration in **app/code/Nik/CatalogGraphQl/etc/schema.graphqls .**
- ` `**Nik\\CatalogGraphQl\\Model\\Resolver\\Story\\CategoryImageIdData** is categoryimageid resolver.
- A graphQL resolver that retrieves data about category images based on city attributes. It iterates over the options of the 'ins\_city' attribute, fetches corresponding category data, and builds an array containing attribute ID, city name, category ID, and category image URL for each category.
- Mytrips configuration in **app/code/Nik/InsidersDashboardGraphQl/etc/schema.graphqls.**
- **Nik\\InsidersDashboardGraphQl\\Model\\Resolver\\MyTripsResolver** is mytrips resolver.
- In resolver for fetching data about trips. It includes methods to handle authorization, retrieve insider and product information, and build a response containing information about top trips with pagination details. The resolver also includes methods to handle image URLs, including placeholders.

**19)categoryinterface:**

- Categoryinterface return data by items.
- esim\_product configuration in **app/code/Nik/CatalogGraphQl/etc/schema.graphqls.**
- **Nik\\CatalogGraphQl\\Model\\Resolver\\Esim** is categoryinterface resolver.
- In  resolver (Esim) that retrieves data about eSIM products based on various filters. The resolver constructs a product collection, applies filters, and returns relevant information in the output arrayTop\_travelpass\_products configuration in **app/code/Nik/CatalogGraphQl/etc/schema.graphqls.**
- **Nik\\CatalogGraphQl\\Model\\Resolver\\Travelpass** is travelpass resolver.
- resolver (**Travelpass**) that retrieves data about top-rated travel passes based on various filters. The resolver constructs a product collection, applies filters, and returns relevant information in the output array. 


** 






