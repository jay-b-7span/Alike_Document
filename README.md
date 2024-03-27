     **This Document for All backend API's**
     
##  **Home Page**

-    **URL**: <https://alike.io/>.
-    **API**: `homepage_stories_products`
    -  This Graphql used for **Handcrafted Holiday Packages** section.
      -  ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/004f3825-6818-4189-9c37-40309ff6f235)
      - **Query**:
        ```graphql
        query homepage_stories_products($pageSize: Int) {
          homepage_stories_products(pageSize: $pageSize) {
            items { 
              uid 
              id
              url_key
              product_likes
              ins_days
              name
              short_description_alike
              ins_tags
              ins_city
              is_liked
              insider_data {
                insider_name
                insider_logo
                insider_id
                profile_url
                is_followed
                username
                __typename
              }
              ins_traveller_type
              image {
                url
                __typename
              }
              icons {
                icon_url
                label
                count
                __typename
              }
              sku
              type_id
              price_range {
                minimum_price {
                  regular_price {
                    value
                    currency
                    __typename
                  }
                  __typename
                }
                __typename
              }
              dynamicAttributes(fields: ["ins_city", "ins_tags"])
              __typename
            }
            __typename
             }
             }
          ```
           
   - **variables:**
        ``` graphql
              {
                 "pageSize": 9
              }
        ```

  - **API:** `currency`
    - This GraphQl is used for **currency**.
    - here are five types of currency code available `GBP`, `EUR`, `INR`, `USD`, `AED`.
    - ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/02b1109d-1dcf-44a3-b7fe-00ec5d0656e4)
    - **Query:**
      ```graphql
          {
           currency {
            ip_currency
            available_currency_codes
            base_currency_code
            base_currency_symbol
            default_display_currecy_code
            default_display_currecy_symbol
            default_display_currency_code
            default_display_currency_symbol
             exchange_rates {s
             currency_to
              rate
              __typename
                }
            __typename
              }
          }
      ```
  - **API:** `new_products`
    - this Graphql used for **Best Selling Experiences** section.
    - ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/2ad1088a-b293-447b-bf7d-8f1f37701048)
    - **Query:**
        ```graphql
            query new_products($input: NewProductsLimit!) {
           new_products(input: $input) {
            url_key
            id
            name
            __typename
            image {
              url
              __typename
            }        
            small_image {
              url
              __typename
            }
            thumbnail {
              url
              __typename
            }
            tour_cities
            tour_category
            exp_duration
            exp_good_for
            exp_languages
            exp_transport_available
            exp_ticket_confirmation
            exp_type_of_ticket
            exp_cancellation
            exp_included_in_touristor
            short_description_alike
            strike_price_value
            price_range {
               maximum_price {
                final_price {
                  value
                  __typename
                }
                __typename
              }
              minimum_price {
                final_price {
                  value
                  __typename
                }
                __typename
              }
              __typename
            }
            dynamicAttributes(fields: ["tour_cities", "tour_category"])
          }
        }
        ```
    - **variables:**
       - ```graphql
             {
                "input": {
                 "limit": 9
                }
             } 
          ```
    - **API:** `cart`
    - Cart GraphQl and Currency GraphQl default set for all pages.
    - ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/316ced0b-c97b-48eb-9a0b-158c2edee01a)
    - **Query:**
       ```graphql
         query cart($cart_id: String!) {
          cart(cart_id: $cart_id) {
            email
            is_virtual
            available_payment_methods {
              code
              title
              description
              know_more
              icon
              merchant_icons
              __typename
            }
            wallet {
              canUseWallet
              walletBalance {
                currency
                value
                __typename
              }
              usedWallet {
                currency
                value
                __typename
              }
              __typename
            }
            billing_address {
              city
              country {
                code
                label
                __typename
              }
              mobile_country_code
              firstname
              lastname
              postcode
              region {
                code
                label
                __typename
              }
              street
              telephone
              __typename
            }
            shipping_addresses {
              firstname
              lastname
              street
              city
              region {
                code
                label
                __typename
              }
              country {
                code
                label
                __typename
              }
              telephone
              available_shipping_methods {
                amount {
                  currency
                  value
                  __typename
                }
                available
                carrier_code
                carrier_title
                error_message
                method_code
                method_title
                price_excl_tax {
                  value
                  currency
                  __typename
                }
                price_incl_tax {
                  value
                  currency
                  __typename
                }
                __typename
              }
              selected_shipping_method {
                amount {
                  value
                  currency
                  __typename
                }
                carrier_code
                carrier_title
                method_code
                method_title
                __typename
              }
              __typename
            }
            items {
              id
              saved_price
              strike_price_value
              product {
                name
                sku
                url_key
                thumbnail {
                  label
                  url
                  __typename
                }
                strike_price_value
                strike_price_percentage
                __typename
              }
              prices {
                price {
                  currency
                  value
                  __typename
                }
                row_total {
                  currency
                  value
                  __typename
                }
                row_total_including_tax {
                  currency
                  value
                  __typename
                }
                total_item_discount {
                  currency
                  value
                  __typename
                }
                __typename
              }
              quantity
              custom_info {
                tour_category
                item_category
                name
                type
                location
                image
                original_price
                saving_price
                custom_options {
                  key
                  label
                  value
                  __typename
                }
                dtpass_jcb_pass_type
                __typename
              }
              __typename
            }
            selected_payment_method {
              code
              title
              __typename
            }
            applied_coupons {
              code
              label
              __typename
            }
            prices {
              applied_taxes {
                amount {
                  currency
                  value
                  __typename
                }
                label
                __typename
              }
              discounts {
                amount {
                  currency
                  value
                  __typename
                }
                label
                __typename
              }
              discount {
                amount {
                  currency
                  value
                  __typename
                }
                __typename
              }
              grand_total {
                value
                currency
                __typename
              }
              subtotal_excluding_tax {
                currency
                value
                __typename
              }
              subtotal_including_tax {
                currency
                value
                __typename
              }
              subtotal_with_discount_excluding_tax {
                currency
                value
                __typename
              }
              fee {
                currency
                value
                __typename
              }
              credit {
                currency
                value
                __typename
              }
              __typename
            }
            __typename
          }
        }
       ```
     - **variables:**
       ```graphql
           {
             "cart_id": "o7WaADKQ6ICyNefpLatbPgMZBqC013hZ"
           }
       ```

## **City Page**
-    **URL:** <https://alike.io/cities/>
-    **API:** `categoryList`
-    This GraphQl is used for serval cities.
-   ![image](https://github.com/jay-b-7span/alike_api_document/assets/114227263/0f3e6104-b748-49af-b7e0-136d72434732)
-    **Query:**
       ```graphql
         query categoryList($filters: CategoryFilterInput) {
          categories(filters: $filters) {
            total_count
            items {
              uid
              level
              name
              url_key
              image
              children {
                uid
                level
                name
                children {
                  uid
                  level
                  name
                  image
                  url_key
                  product_count
                  highlights {
                    title
                    url
                    __typename
                  }
                  __typename
                }
                __typename
              }
              __typename
            }
            __typename
          }
        }
       ```
   **variables:**
   ```graphql
        {
          "filters": {
            "parent_id": {
              "in": [
                "717"
              ]
            },
            "category_uid": {
              "in": [
                "NzE4",
                "NzI1",
                "NzQ5",
                "ODE3",
                "ODY3",
                "ODc2"
              ]
            }
          }
        }
   ```
-   **API:** `Cities`
-   This GraphQl used for **Best Places to visit** section.
-   ![image](https://github.com/jay-b-7span/alike_api_document/assets/114227263/4392e211-fc8a-4051-b4b6-baf7121dffbb)
-   **Query:**
    ```graphql
        {
          Cities {
            best {
              title
              months {
                city {
                  highlights {
                    title
                    url
                    __typename
                  }
                  category_id
                  category_uid
                  image
                  name
                  url_key
                  __typename
                }
                month
                __typename
              }
              __typename
            }
            mostVisited {
              title
              city {
                highlights {
                  title
                  url
                  __typename
                }
                category_id
                category_uid
                image
                name
                url_key
                __typename
              }
              __typename
            }
            discover {
              title
              city {
                highlights {
                  title
                  url
                  __typename
                }
                category_id
                category_uid
                image
                name
                url_key
                __typename
              }
              __typename
            }
            __typename
          }
        }
     ```
## **City Detail Page**
-    **URL:** <https://alike.host/cities/dubai>
-    **API:** `categories`
-    Here categories GraphQl used for preticular city details and also used fro **faq** section.
-    ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/aede09c7-df8e-44c0-bb86-443ebc2025cf)
-    **Query:**
     ```graphql
         query categories($filters: CategoryFilterInput) {
          categories(filters: $filters) {
            items {
              uid
              id
              name
              url_key
              latitude_longitude
              weather_description
              best_time_to_visit {
                best_month_to_visit
                things_to_do
                __typename
              }
              months_weather {
                months
                temperature
                __typename
              }
              city_currency
              city_timezone
              city_faqs {
                questions
                answers
                __typename
              }
              __typename
            }
            __typename
          }
        }
     ```
-    **variables:**
     ```graphql
        {
          "filters": {
            "ids": {
              "eq": 720
            }
          }
        }
     ```
-    **API:** `products`
-    This GraphQl used for a particular product's detail here **Filters** block.
-    ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/c9427ad2-9078-4114-9af1-0ee94f8ee5e0)
-    **Query:**
-    ```graphql
         query products($search: String, $filter: ProductAttributeFilterInput, $pageSize: Int, $currentPage: Int, $sort: ProductAttributeSortInput) {
          products(
            search: $search
            filter: $filter
            pageSize: $pageSize
            currentPage: $currentPage
            sort: $sort
          ) {
            aggregations {
              attribute_code
              count
              label
              options {
                count
                label
                value
                __typename
              }
              __typename
            }
            items {
              uid
              id
              url_key
              product_likes
              ins_days
              name
              short_description_alike
              ins_tags
              ins_city
              strike_price_value
              strike_price_percentage
              dynamicAttributes(
                fields: ["tour_cities", "ins_city", "tour_category", "ins_tags"]
              )
              is_liked
              insider_data {
                insider_name
                insider_logo
                insider_id
                profile_url
                is_followed
                username
                __typename
              }
              ins_traveller_type
              __typename
              image {
                url
                __typename
              }
              small_image {
                url
                __typename
              }
              thumbnail {
                url
                __typename
              }
              sku
              type_id
              tour_cities
              tour_category
              exp_duration
              exp_good_for
              exp_languages
              exp_transport_available
              exp_ticket_confirmation
              exp_type_of_ticket
              exp_cancellation
              exp_included_in_touristor
              price_range {
                maximum_price {
                  regular_price {
                    value
                    currency
                    __typename
                  }
                  final_price {
                    value
                    __typename
                  }
                  __typename
                }
                minimum_price {
                  regular_price {
                    value
                    currency
                    __typename
                  }
                  final_price {
                    value
                    __typename
                  }
                  __typename
                }
                __typename
              }
            }
            custom {
              filters {
                attribute_code
                attribute_value
                image
                title
                __typename
              }
              __typename
            }
            sort_fields {
              default
              options {
                label
                value
                __typename
              }
              __typename
            }
            related_search_terms
            did_you_know
            total_count
            page_info {
              current_page
              page_size
              total_pages
              __typename
            }
            __typename
          }
        }
     ```
-    **variables:**
     ```graphql
        {
          "currentPage": 1,
          "pageSize": 6,
          "search": "",
          "filter": {
            "tour_category": {
              "in": []
            },
            "item_category": {
              "in": []
            },
            "category_id": {
              "in": [
                720
              ]
            },
            "insider_approval": {
              "eq": "2"
            }
          },
          "sort": {}
        }
     ```
-    **API:** `categoryList`
-    ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/ffb2c1cd-4146-469b-92ce-32f7b0226549)
-    **Query:**
      ```graphql
        query categoryList($filters: CategoryFilterInput) {
          categoryList(filters: $filters) {
            name
            uid
            id
            custom {
              banner_title
              banner_description
              banner_image
              hide_activity
              hide_story
              filters {
                title
                image
                attribute_code
                attribute_value
                __typename
              }
              know_more_about {
                content
                identifier
                title
                __typename
              }
              faq {
                content
                identifier
                title
                __typename
              }
              __typename
            }
            activities_products {
              title
              items {
                id
                uid
                sku
                url_key
                name
                dynamicAttributes(fields: ["tour_cities", "tour_category"])
                exp_cancellation
                exp_duration
                review_count
                rating_summary
                image {
                  url
                  __typename
                }
                small_image {
                  url
                  __typename
                }
                thumbnail {
                  url
                  __typename
                }
                price_range {
                  minimum_price {
                    final_price {
                      value
                      currency
                      __typename
                    }
                    __typename
                  }
                  __typename
                }
                __typename
              }
              __typename
            }
            stories_products {
              title
              items {
                uid
                id
                url_key
                product_likes
                ins_days
                name
                short_description_alike
                ins_tags
                ins_city
                icons {
                  icon_url
                  label
                  count
                  __typename
                }
                dynamicAttributes(fields: ["ins_city", "ins_traveller_type", "ins_tags"])
                is_liked
                insider_data {
                  insider_name
                  insider_logo
                  insider_id
                  profile_url
                  is_followed
                  username
                  __typename
                }
                ins_traveller_type
                image {
                  url
                  __typename
                }
                small_image {
                  url
                  __typename
                }
                icons {
                  icon_url
                  label
                  count
                  __typename
                }
                sku
                type_id
                price_range {
                  maximum_price {
                    regular_price {
                      value
                      currency
                      __typename
                    }
                    __typename
                  }
                  minimum_price {
                    regular_price {
                      value
                      currency
                      __typename
                    }
                    __typename
                  }
                  __typename
                }
                __typename
              }
              __typename
            }
            __typename
          }
        }
     ```
-    **variables:**
     ```graphql
        {
          "filters": {
            "url_key": {
              "eq": "singapore"
            }
          }
        }
     ```
 ## **Product Page:**
 -    **URL:** <https://alike.io/products/farewell-tour-half-day-dubai-city-tour>
 -    **API:** `products`
 -    This is GraphQl also used for product detail page.
 -    ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/e865a99d-800f-4286-af2e-49b22e2e8054)
-    **Query:**
     ```graphql
         query products($search: String, $filter: ProductAttributeFilterInput) {
          products(search: $search, filter: $filter) {
            items {
              api_connected
              api_connected_label
              attribute_set_id
              available_from
              available_to
              musement_id
              url_key
              sku
              id
              name
              categories {
                name
                uid
                url_key
                level
                __typename
              }
              ticket_advance_time
              strike_price_value
              strike_price_percentage
              __typename
              ... on BundleProduct {
                items {
                  options {
                    position
                    product {
                      sku
                      id
                      name
                      is_transfer
                      strike_price_value
                      strike_price_percentage
                      pass_included_zomato
                      pass_included_text_zomato
                      pass_included_tour
                      pass_included_text_tour
                      pass_included_sim
                      pass_included_text_sim
                      pass_included_wifi
                      pass_included_text_wifi
                      pass_included_nol
                      pass_included_text_nol
                      pass_included_visa
                      pass_included_text_visa
                      price_range {
                        minimum_price {
                          final_price {
                            value
                            __typename
                          }
                          __typename
                        }
                        __typename
                      }
                      exp_included
                      exp_excluded
                      touristor_saver {
                        final_price
                        image
                        label
                        name
                        original_price
                        type
                        __typename
                      }
                      hide_adult
                      hide_child
                      hide_infant
                      kit_availability {
                        available {
                          from
                          to
                          __typename
                        }
                        kit_id
                        name
                        not_available
                        price
                        price_adult
                        price_child
                        timeslots
                        transfer_type
                        type
                        __typename
                      }
                      __typename
                    }
                    __typename
                  }
                  __typename
                }
                __typename
              }
              globaltix_availability {
                activity_id
                id
                name
                price
                variations {
                  id
                  isOpenDated
                  maximumPax
                  minimumPax
                  name
                  type
                  visitDate {
                    advanceBookingDays
                    advanceBookingHours
                    advanceBookingMinutes
                    class
                    id
                    isAdvanceBooking
                    isRequestVisitDate
                    isVisitDateCompulsory
                    ticketTypeGroup {
                      class
                      id
                      __typename
                    }
                    __typename
                  }
                  __typename
                }
                __typename
              }
              is_transfer
              adult_label
              hide_adult
              hide_child
              hide_infant
              kit_availability {
                available {
                  from
                  to
                  timeslots
                  __typename
                }
                kit_id
                name
                not_available
                price
                price_adult
                price_child
                timeslots
                transfer_type
                type
                __typename
              }
              image {
                url
                __typename
              }
              tour_cities
              exp_itinerary
              tour_category
              exp_duration
              exp_good_for
              exp_languages
              exp_transport_available
              exp_ticket_confirmation
              exp_type_of_ticket
              exp_cancellation
              exp_included_in_touristor
              short_description_alike
              exp_included
              exp_excluded
              exp_more_information
              description_alike
              exp_cancellation_policy
              exp_child_policy
              exp_activity_details
              exp_address
              exp_timings
              rayna_id
              rayna_country_id
              rayna_city_id
              rayna_contract_id
              media_gallery {
                url
                label
                disabled
                __typename
              }
              included_in_touristors {
                url_key
                id
                name
                dynamicAttributes(fields: ["tour_cities", "tour_category"])
                exp_cancellation
                exp_duration
                exp_good_for
                price_range {
                  minimum_price {
                    final_price {
                      value
                      currency
                      __typename
                    }
                    __typename
                  }
                  __typename
                }
                image {
                  url
                  __typename
                }
                small_image {
                  url
                  __typename
                }
                thumbnail {
                  url
                  __typename
                }
                __typename
              }
              included_trips {
                uid
                id
                url_key
                product_likes
                ins_days
                name
                short_description_alike
                ins_tags
                ins_city
                is_liked
                dynamicAttributes(fields: ["ins_city", "ins_traveller_type", "ins_tags"])
                insider_data {
                  insider_name
                  insider_logo
                  insider_id
                  profile_url
                  is_followed
                  username
                  __typename
                }
                ins_traveller_type
                image {
                  url
                  __typename
                }
                small_image {
                  url
                  __typename
                }
                thumbnail {
                  url
                  __typename
                }
                story_icons_count
                icons {
                  icon_url
                  label
                  count
                  __typename
                }
                sku
                type_id
                price_range {
                  maximum_price {
                    regular_price {
                      value
                      currency
                      __typename
                    }
                    __typename
                  }
                  minimum_price {
                    regular_price {
                      value
                      currency
                      __typename
                    }
                    __typename
                  }
                  __typename
                }
                __typename
              }
              related_products {
                url_key
                id
                name
                dynamicAttributes(fields: ["tour_cities", "tour_category"])
                exp_cancellation
                exp_duration
                exp_good_for
                price_range {
                  minimum_price {
                    final_price {
                      value
                      currency
                      __typename
                    }
                    __typename
                  }
                  __typename
                }
                image {
                  url
                  __typename
                }
                small_image {
                  url
                  __typename
                }
                thumbnail {
                  url
                  __typename
                }
                __typename
              }
              price_range {
                maximum_price {
                  final_price {
                    value
                    __typename
                  }
                  __typename
                }
                minimum_price {
                  final_price {
                    value
                    __typename
                  }
                  __typename
                }
                __typename
              }
              pass_included_zomato
              pass_included_text_zomato
              pass_included_tour
              pass_included_text_tour
              pass_included_sim
              pass_included_text_sim
              pass_included_wifi
              pass_included_text_wifi
              pass_included_nol
              pass_included_text_nol
              pass_included_visa
              pass_included_text_visa
              touristor_saver {
                final_price
                image
                label
                name
                order
                original_price
                type
                url_key
                tour_category
                __typename
              }
              dynamicAttributes(
                fields: ["tour_cities", "exp_languages", "exp_good_for", "tour_category", "off_days", "api_connected", "api_connected_label"]
              )
            }
            total_count
            page_info {
              current_page
              page_size
              total_pages
              __typename
            }
            __typename
          }
        }
     ```
-    **variables:**
     ```graphql
        {
          "filter": {
            "url_key": {
              "eq": "farewell-tour-half-day-dubai-city-tour"
            }
          },
          "pageSize": 1,
          "currentPage": 1
        }
     ```
-    **API:** `getRaynaTickets`
-    this API used for ticket.
-    ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/7e58652b-a11f-4cb0-bda4-ad7391500bbd)
-    **Query:**
     ```graphql
       query getRaynaTickets($input: RaynaProductInput!) {
          getRaynaTickets(input: $input) {
            default
            display_price
            id
            name
            __typename
          }
        }
     ```
-    **variables:**
     ```graphql
         {
          "input": {
            "id": "5116",
            "product_id": 2490,
            "group": "group_r",
            "transfer": "41865",
            "date": "2024/03/29",
            "contract": "300"
          }
        }
     ```   
-    **API:** `getProduct`
-    ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/ef1b018a-6176-4edd-aca1-3ed3dd71df0a)
-    **Query:**
      ```graphql
         query getProduct($input: RaynaProductInput!) {
          getProduct(input: $input) {
            transfer_type {
              id
              is_default
              max_pax
              min_pax
              name
              __typename
            }
            __typename
          }
        }
      ```
-    **variables:**
      ```graphql
        {
          "input": {
            "id": "5116",
            "product_id": 2490,
            "group": "group_r",
            "country": "13063",
            "city": "13668",
            "contract": "300"
          }
        }
      ```
-    **API:** `globaltix_variation_type`
-    this API used for ticket selection in product page.
-    ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/cce576b5-069d-4dc9-a0aa-e69e3e83051d)
-    **Query:**
      ```graphql
         query globaltix_variation_type($product_id: String, $variation_id: [String]) {
          globaltix_variation_type(product_id: $product_id, variation_id: $variation_id) {
            tickets {
              id
              advanceBookingDays
              applyCapacity
              availability
              isAdvanceBooking
              isRequestVisitDate
              isVisitDateCompulsory
              price
              publishEnd
              publishStart
              questions {
                class
                id
                optional
                options
                question
                tourInfo
                type {
                  enumType
                  name
                  __typename
                }
                __typename
              }
              series
              status
              __typename
            }
            __typename
          }
        }
      ```
-    **variables:**
      ```graphql
        {
          "variation_id": [
            "61532",
            "61533"
          ],
          "product_id": "2074"
        }
      ```

## **Hotel Page**
-   **URL:** <https://alike.io/hotels/list?search=Dubai,%20United%20Arab%20Emirates&destinations=ChIJRcbZaklDXz4RYlEphFBu5r0&checkIn=2024-04-04&checkOut=2024-04-06&occupancies=%5B%7B%22paxes%22%3A%5B%7B%22age%22%3A25%7D,%7B%22age%22%3A29%7D%5D%7D%5D>
-   **API:** `searchListGuzzleX`
-   this API is used for serval hotels in particular cities.
-   ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/4e1020b5-27df-49dd-a752-efbb8f2a6eee)
-   **Query:**
    ```graphql
        query searchListGuzzleX($checkIn: String!, $checkOut: String!, $session: String, $occupancies: [RoomInputX!]!, $slug: String, $destinations: [String!], $hotels: [String!], $pageSize: Int, $onlyStatic: 
        Boolean, $currentPage: Int, $sort: HotelSortXInput, $filter: [HotelFiltersXInput]) {
          searchListGuzzleX(
            checkIn: $checkIn
            checkOut: $checkOut
            session: $session
            occupancies: $occupancies
            slug: $slug
            destinations: $destinations
            hotels: $hotels
            pageSize: $pageSize
            onlyStatic: $onlyStatic
            currentPage: $currentPage
            sort: $sort
            filter: $filter
          ) {
            error
            hotels {
              static
              hotelCode
              destinationCode
              slug
              status
              name
              title
              boardCode
              cancelPolicy {
                cancelPenalties {
                  currency
                  deadline
                  hoursBefore
                  penaltyType
                  value
                  __typename
                }
                refundable
                __typename
              }
              amenities {
                amenityCodeSupplier
                code
                texts
                type
                value
                __typename
              }
              occupancies {
                id
                paxes {
                  age
                  __typename
                }
                __typename
              }
              rating
              userRating
              mainImage {
                code
                label
                order
                type
                url
                __typename
              }
              medias {
                code
                label
                order
                type
                url
                __typename
              }
              minRate {
                currency
                net
                __typename
              }
              maxRate {
                currency
                net
                __typename
              }
              displayPrice {
                currency
                net
                __typename
              }
              propertyType
              chainName
              brandName
              popularityScore
              contentScore
              remarks
              location {
                address
                city
                state
                zipCode
                country
                coordinates {
                  label
                  latitude
                  longitude
                  __typename
                }
                __typename
              }
              descriptions {
                text
                type
                __typename
              }
              amenities {
                amenityCodeSupplier
                code
                texts
                type
                value
                __typename
              }
              facilities {
                code
                title
                items {
                  code
                  name
                  __typename
                }
                __typename
              }
              reviews {
                count
                highlightText
                rating
                tagLine
                type
                __typename
              }
              contact {
                email
                fax
                telephone
                web
                __typename
              }
              filters {
                code
                values
                __typename
              }
              options {
                tax {
                  net
                  currency
                  __typename
                }
                id
                accommodationType
                boardLabel
                amenities {
                  amenityCodeSupplier
                  code
                  texts
                  type
                  value
                  __typename
                }
                boardCode
                boardLabel
                cancelPolicy {
                  cancelPenalties {
                    currency
                    deadline
                    hoursBefore
                    penaltyType
                    value
                    __typename
                  }
                  refundable
                  __typename
                }
                descriptions {
                  type
                  text
                  __typename
                }
                price {
                  currency
                  net
                  __typename
                }
                occupancies {
                  id
                  paxes {
                    age
                    __typename
                  }
                  __typename
                }
                remarks
                filters {
                  code
                  values
                  __typename
                }
                rooms {
                  facilities {
                    code
                    title
                    items {
                      code
                      name
                      __typename
                    }
                    __typename
                  }
                  tax {
                    net
                    currency
                    __typename
                  }
                  amenities {
                    amenityCodeSupplier
                    code
                    texts
                    type
                    value
                    __typename
                  }
                  beds {
                    count
                    shared
                    type
                    __typename
                  }
                  code
                  description
                  features {
                    code
                    __typename
                  }
                  legacyRoomId
                  medias {
                    code
                    label
                    order
                    type
                    url
                    __typename
                  }
                  name
                  occupancyRefId
                  promotions {
                    code
                    start
                    end
                    name
                    __typename
                  }
                  ratePlans {
                    code
                    start
                    end
                    name
                    supplierCode
                    __typename
                  }
                  refundable
                  roomPrice {
                    breakdown {
                      start
                      end
                      price {
                        currency
                        net
                        __typename
                      }
                      __typename
                    }
                    price {
                      currency
                      net
                      __typename
                    }
                    __typename
                  }
                  supplierCode
                  surcharges {
                    chargeType
                    code
                    description
                    mandatory
                    price {
                      currency
                      net
                      __typename
                    }
                    __typename
                  }
                  units
                  __typename
                }
                __typename
              }
              __typename
            }
            maps {
              label
              slug
              latitude
              longitude
              __typename
            }
            isStaticRecords
            pagination {
              current
              full
              page
              total
              __typename
            }
            filters {
              code
              label
              options {
                code
                count
                name
                __typename
              }
              __typename
            }
            __typename
          }
        }
    ```
-   **variables:**
     ```graphql
        {
          "checkIn": "2024-04-04",
          "checkOut": "2024-04-06",
          "currentPage": 1,
          "pageSize": 10,
          "search": "",
          "occupancies": [
            {
              "paxes": [
                {
                  "age": 25
                },
                {
                  "age": 29
                }
              ]
            }
          ],
          "destinations": [
            "ChIJRcbZaklDXz4RYlEphFBu5r0"
          ],
          "slug": "",
          "filter": [],
          "sort": {
            "by": "distance",
            "order": "ASC"
          },
          "onlyStatic": true
        }
     ```
-    **API:** `searchListGuzzleX`
-    this API used for filtration like Star **Rating**, **Property Type**, **Meals**, **Cancellation** etc.
-    ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/39bd6525-b2d2-42ee-8441-90d523c53d7d)
-    **Query:**
      ```graphql
         query searchListGuzzleX($checkIn: String!, $checkOut: String!, $session: String, $occupancies: [RoomInputX!]!, $slug: String, $destinations: [String!], $hotels: [String!], $pageSize: Int, 
         $onlyStatic: Boolean, $currentPage: Int, $sort: HotelSortXInput, $filter: [HotelFiltersXInput]) {
          searchListGuzzleX(
            checkIn: $checkIn
            checkOut: $checkOut
            session: $session
            occupancies: $occupancies
            slug: $slug
            destinations: $destinations
            hotels: $hotels
            pageSize: $pageSize
            onlyStatic: $onlyStatic
            currentPage: $currentPage
            sort: $sort
            filter: $filter
          ) {
            error
            hotels {
              static
              hotelCode
              destinationCode
              slug
              status
              name
              title
              boardCode
              cancelPolicy {
                cancelPenalties {
                  currency
                  deadline
                  hoursBefore
                  penaltyType
                  value
                  __typename
                }
                refundable
                __typename
              }
              amenities {
                amenityCodeSupplier
                code
                texts
                type
                value
                __typename
              }
              occupancies {
                id
                paxes {
                  age
                  __typename
                }
                __typename
              }
              rating
              userRating
              mainImage {
                code
                label
                order
                type
                url
                __typename
              }
              medias {
                code
                label
                order
                type
                url
                __typename
              }
              minRate {
                currency
                net
                __typename
              }
              maxRate {
                currency
                net
                __typename
              }
              displayPrice {
                currency
                net
                __typename
              }
              propertyType
              chainName
              brandName
              popularityScore
              contentScore
              remarks
              location {
                address
                city
                state
                zipCode
                country
                coordinates {
                  label
                  latitude
                  longitude
                  __typename
                }
                __typename
              }
              descriptions {
                text
                type
                __typename
              }
              amenities {
                amenityCodeSupplier
                code
                texts
                type
                value
                __typename
              }
              facilities {
                code
                title
                items {
                  code
                  name
                  __typename
                }
                __typename
              }
              reviews {
                count
                highlightText
                rating
                tagLine
                type
                __typename
              }
              contact {
                email
                fax
                telephone
                web
                __typename
              }
              filters {
                code
                values
                __typename
              }
              options {
                tax {
                  net
                  currency
                  __typename
                }
                id
                accommodationType
                boardLabel
                amenities {
                  amenityCodeSupplier
                  code
                  texts
                  type
                  value
                  __typename
                }
                boardCode
                boardLabel
                cancelPolicy {
                  cancelPenalties {
                    currency
                    deadline
                    hoursBefore
                    penaltyType
                    value
                    __typename
                  }
                  refundable
                  __typename
                }
                descriptions {
                  type
                  text
                  __typename
                }
                price {
                  currency
                  net
                  __typename
                }
                occupancies {
                  id
                  paxes {
                    age
                    __typename
                  }
                  __typename
                }
                remarks
                filters {
                  code
                  values
                  __typename
                }
                rooms {
                  facilities {
                    code
                    title
                    items {
                      code
                      name
                      __typename
                    }
                    __typename
                  }
                  tax {
                    net
                    currency
                    __typename
                  }
                  amenities {
                    amenityCodeSupplier
                    code
                    texts
                    type
                    value
                    __typename
                  }
                  beds {
                    count
                    shared
                    type
                    __typename
                  }
                  code
                  description
                  features {
                    code
                    __typename
                  }
                  legacyRoomId
                  medias {
                    code
                    label
                    order
                    type
                    url
                    __typename
                  }
                  name
                  occupancyRefId
                  promotions {
                    code
                    start
                    end
                    name
                    __typename
                  }
                  ratePlans {
                    code
                    start
                    end
                    name
                    supplierCode
                    __typename
                  }
                  refundable
                  roomPrice {
                    breakdown {
                      start
                      end
                      price {
                        currency
                        net
                        __typename
                      }
                      __typename
                    }
                    price {
                      currency
                      net
                      __typename
                    }
                    __typename
                  }
                  supplierCode
                  surcharges {
                    chargeType
                    code
                    description
                    mandatory
                    price {
                      currency
                      net
                      __typename
                    }
                    __typename
                  }
                  units
                  __typename
                }
                __typename
              }
              __typename
            }
            maps {
              label
              slug
              latitude
              longitude
              __typename
            }
            isStaticRecords
            pagination {
              current
              full
              page
              total
              __typename
            }
            filters {
              code
              label
              options {
                code
                count
                name
                __typename
              }
              __typename
            }
            __typename
          }
        }
      ```
-    **variables:**
     ```graphql
        {
          "checkIn": "2024-04-04",
          "checkOut": "2024-04-06",
          "currentPage": 1,
          "pageSize": 10,
          "search": "",
          "occupancies": [
            {
              "paxes": [
                {
                  "age": 25
                },
                {
                  "age": 29
                }
              ]
            }
          ],
          "destinations": [
            "ChIJRcbZaklDXz4RYlEphFBu5r0"
          ],
          "slug": "",
          "filter": [],
          "sort": {
            "by": "distance",
            "order": "ASC"
          },
          "onlyStatic": false
        }
     ```
     
##  **Hotel Detail Page**
-   **URL:** <https://alike.io/hotels/lapita-dubai-parks-resorts-autograph-collection-in-united-arab-emirates-dubai--lapita_dubai_parks_and_resorts?search=Dubai,%20United%20Arab%20Emirates&destinations=ChIJRcbZaklDXz4RYlEphFBu5r0&checkIn=2024-04-04&checkOut=2024-04-06&occupancies=%5B%7B%22paxes%22%3A%5B%7B%22age%22%3A25%7D,%7B%22age%22%3A29%7D%5D%7D%5D>
-   **API:** `searchX`
-   ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/3b100555-74cf-4057-8f0c-dfcb95a6dc52)
-   **Query:**
     ```graphql
         query searchX($checkIn: String!, $checkOut: String!, $session: String, $occupancies: [RoomInputX!]!, $slug: String, $destinations: [String!], $hotels: [String!], $pageSize: Int, $maxSize: Int, 
         $currentPage: Int, $sort: HotelSortXInput, $filter: [HotelFiltersXInput]) {
          searchX(
            checkIn: $checkIn
            checkOut: $checkOut
            session: $session
            occupancies: $occupancies
            slug: $slug
            destinations: $destinations
            hotels: $hotels
            pageSize: $pageSize
            maxSize: $maxSize
            currentPage: $currentPage
            sort: $sort
            filter: $filter
          ) {
            error
            hotels {
              hotelCode
              destinationCode
              slug
              status
              name
              title
              boardCode
              cancelPolicy {
                cancelPenalties {
                  currency
                  deadline
                  hoursBefore
                  penaltyType
                  value
                  __typename
                }
                refundable
                __typename
              }
              amenities {
                amenityCodeSupplier
                code
                texts
                type
                value
                __typename
              }
              occupancies {
                id
                paxes {
                  age
                  __typename
                }
                __typename
              }
              rating
              userRating
              mainImage {
                code
                label
                order
                type
                url
                __typename
              }
              medias {
                code
                label
                order
                type
                url
                __typename
              }
              minRate {
                currency
                net
                __typename
              }
              maxRate {
                currency
                net
                __typename
              }
              displayPrice {
                currency
                net
                __typename
              }
              propertyType
              chainName
              brandName
              popularityScore
              contentScore
              remarks
              location {
                address
                city
                state
                zipCode
                country
                coordinates {
                  label
                  latitude
                  longitude
                  __typename
                }
                __typename
              }
              descriptions {
                text
                type
                __typename
              }
              amenities {
                amenityCodeSupplier
                code
                texts
                type
                value
                __typename
              }
              facilities {
                code
                title
                items {
                  code
                  name
                  __typename
                }
                __typename
              }
              reviews {
                count
                highlightText
                rating
                tagLine
                type
                __typename
              }
              contact {
                email
                fax
                telephone
                web
                __typename
              }
              filters {
                code
                values
                __typename
              }
              options {
                tax {
                  net
                  currency
                  __typename
                }
                id
                accommodationType
                boardLabel
                amenities {
                  amenityCodeSupplier
                  code
                  texts
                  type
                  value
                  __typename
                }
                boardCode
                boardLabel
                cancelPolicy {
                  cancelPenalties {
                    currency
                    deadline
                    hoursBefore
                    penaltyType
                    value
                    __typename
                  }
                  refundable
                  __typename
                }
                descriptions {
                  type
                  text
                  __typename
                }
                price {
                  currency
                  net
                  __typename
                }
                occupancies {
                  id
                  paxes {
                    age
                    __typename
                  }
                  __typename
                }
                remarks
                filters {
                  code
                  values
                  __typename
                }
                rooms {
                  facilities {
                    code
                    title
                    items {
                      code
                      name
                      __typename
                    }
                    __typename
                  }
                  tax {
                    net
                    currency
                    __typename
                  }
                  amenities {
                    amenityCodeSupplier
                    code
                    texts
                    type
                    value
                    __typename
                  }
                  beds {
                    count
                    shared
                    type
                    __typename
                  }
                  code
                  description
                  features {
                    code
                    __typename
                  }
                  legacyRoomId
                  medias {
                    code
                    label
                    order
                    type
                    url
                    __typename
                  }
                  name
                  occupancyRefId
                  promotions {
                    code
                    start
                    end
                    name
                    __typename
                  }
                  ratePlans {
                    code
                    start
                    end
                    name
                    supplierCode
                    __typename
                  }
                  refundable
                  roomPrice {
                    breakdown {
                      start
                      end
                      price {
                        currency
                        net
                        __typename
                      }
                      __typename
                    }
                    price {
                      currency
                      net
                      __typename
                    }
                    __typename
                  }
                  supplierCode
                  surcharges {
                    chargeType
                    code
                    description
                    mandatory
                    price {
                      currency
                      net
                      __typename
                    }
                    __typename
                  }
                  units
                  __typename
                }
                __typename
              }
              __typename
            }
            maps {
              label
              slug
              latitude
              longitude
              __typename
            }
            isStaticRecords
            pagination {
              current
              full
              page
              total
              __typename
            }
            filters {
              code
              label
              options {
                code
                count
                name
                __typename
              }
              __typename
            }
            __typename
          }
        }
     ```
-   **variables:**
    ```graphql
         {
          "checkIn": "2024-04-04",
          "checkOut": "2024-04-06",
          "currentPage": 1,
          "pageSize": 10,
          "search": "",
          "occupancies": [
            {
              "paxes": [
                {
                  "age": 25
                },
                {
                  "age": 29
                }
              ]
            }
          ],
          "destinations": [],
          "slug": "lapita-dubai-parks-resorts-autograph-collection-in-united-arab-emirates-dubai--lapita_dubai_parks_and_resorts",
          "filter": [],
          "sort": {
            "by": "price",
            "order": "ASC"
          }
        }
     ```
-    **API:** `products`
-    ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/7e0b456b-8294-4fff-b373-96190f7249cb)
-    **Query:**
     ```graphql
         query products($filter: ProductAttributeFilterInput) {
          products(filter: $filter) {
            items {
              uid
              id
              url_key
              name
              short_description {
                html
                __typename
              }
              description {
                html
                __typename
              }
              strike_price_value
              strike_price_percentage
              sku
              type_id
              hotel_property_type
              hotel_rating
              hotel_city_name
              hotel_country_code
              hotel_country_name
              hotel_latitude
              hotel_longitude
              hotel_facilities
              hotel_board_types
              hotel_cancellation_policies
              image {
                url
                __typename
              }
              price_range {
                maximum_price {
                  regular_price {
                    value
                    currency
                    __typename
                  }
                  final_price {
                    value
                    __typename
                  }
                  __typename
                }
                minimum_price {
                  regular_price {
                    value
                    currency
                    __typename
                  }
                  final_price {
                    value
                    __typename
                  }
                  __typename
                }
                __typename
              }
              media_gallery {
                url
                label
                disabled
                __typename
              }
              __typename
            }
            sort_fields {
              default
              options {
                label
                value
                __typename
              }
              __typename
            }
            related_search_terms
            did_you_know
            total_count
            page_info {
              current_page
              page_size
              total_pages
              __typename
            }
            __typename
          }
        }
     ```
-   **variables:**
    ```graphql
        {
          "filter": {
            "url_key": {
              "eq": "lapita-dubai-parks-resorts-autograph-collection-in-united-arab-emirates-dubai--lapita_dubai_parks_and_resorts"
            }
          }
        }
    ```

##  **Tourist Plan Page**
-    **URL:** <https://alike.io/tourist-plan>
-    **API:** `touristPlans`
-    ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/45f26314-0aa4-4b75-ad4c-91818bc2ecf7)
-    **Query:**
      ```graphql
        {
          touristPlans {
            data
            data_label
            minute
            name
            price
            sort_order
            validity
            product_id
            unlimited_internet_calls
            attraction_discount
            most_popular
            best_value
            __typename
          }
        }
      ```
-   **API:** `cmsPage`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/12ec604c-d156-4ede-9dda-2085bd73cd7b)
-   **Query:**
    ```graphql
        query cmsPage($identifier: String) {
          cmsPage(identifier: $identifier) {
            identifier
            url_key
            title
            meta_title
            meta_description
            meta_keywords
            __typename
          }
        }
     ```
-   **variables:**
    ```graphql:
        {
          "identifier": "tourist-plan"
        }
     ```
