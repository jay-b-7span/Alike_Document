     **This Document for All backend API's**
     
##  **Home Page**

-    **URL**: <https://alike.io/>.
-    **API**: `homepage_stories_products`
-    This API used for **Handcrafted Holiday Packages** section.
-    ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/713bc382-539b-47a3-a219-a99290e6d42f)
-    **Query**:
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
           
-    **variables:**
     ```graphql
             {
                 "pageSize": 9
             }
        ```

-   **API:** `currency`
-    This GraphQl is used for **currency**.
-    here are five types of currency code available `GBP`, `EUR`, `INR`, `USD`, `AED`.
-    ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/02b1109d-1dcf-44a3-b7fe-00ec5d0656e4)
-    **Query:**
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
-    **API:** `new_products`
-    this Graphql used for **Best Selling Experiences** section.
-    ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/2ad1088a-b293-447b-bf7d-8f1f37701048)
-    **Query:**
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
-    **variables:**
        ```graphql
             {
                "input": {
                 "limit": 9
                }
             } 
          ```
-    **API:** `cart`
-    Cart GraphQl and Currency GraphQl default set for all pages.
-   ![image](https://github.com/jay-b-7span/Alike_API_Documentation/assets/114227263/316ced0b-c97b-48eb-9a0b-158c2edee01a)
-   **Query:**
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
-   This API used for **Best Places to visit** section.
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
-    Here categories API used for preticular city details and also used fro **faq** section.
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
-    This API used for a particular product's detail here **Filters** block.
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
     
##  **Product Page**
 -    **URL:** <https://alike.io/products/farewell-tour-half-day-dubai-city-tour>
 -    **API:** `products`
 -    This is API also used for product detail page.
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
-  **API:** `storeConfig`
-  **Query:**
    ```grqphql
        {
          storeConfig {
            custom_general_rental_price
            custom_general_rental_free
            __typename
          }
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
-   **API:** `customerCart`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/f9b3afc0-93ae-4e9c-8554-5951bd75bd1a)
-   **Query:**
    ```graphql
        {
          customerCart {
            id
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
                __typename
              }
              prices {
                price {
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
                __typename
              }
              __typename
            }
            total_quantity
            prices {
              grand_total {
                value
                currency
                __typename
              }
              __typename
            }
            __typename
          }
        }
    ```

    
##  **Travel Passes Page**
-   **URL:** <https://alike.io/travel-passes?utm_source=site&utm_medium=menu-desktop&utm_campaign=menu>
-   **API:** `categories`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/34422e77-0bf8-4051-b56c-8e1ce06aca84)
-   **Query:**
     ```graphql
        query categories($filters: CategoryFilterInput) {
          categories(filters: $filters) {
            total_count
            items {
              uid
              level
              name
              path
              esim_products {
                title
                items {
                  url_key
                  id
                  name
                  __typename
                  image {
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
                __typename
              }
              top_travelpass_products {
                title
                items {
                  url_key
                  id
                  name
                  __typename
                  image {
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
                __typename
              }
              __typename
            }
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
-   **API:** `products`
-   this API is used to show products on the travel passes page.
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/7e35feb0-1959-4b41-b28e-279558895402)
-   **Query:**
    ```garphql
        query products($search: String, $filter: ProductAttributeFilterInput, $pageSize: Int, $currentPage: Int, $sort: ProductAttributeSortInput) {
          products(
            search: $search
            filter: $filter
            pageSize: $pageSize
            currentPage: $currentPage
            sort: $sort
          ) {
            total_count
            items {
              sort_order
              url_key
              name
              country_of_manufacture
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
                    currency
                    value
                    __typename
                  }
                  __typename
                }
                __typename
              }
              is_liked
              ins_city
              dynamicAttributes(fields: ["ins_city", "ins_tags"])
              attribute_set_id
              __typename
            }
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
     ```garphql
        {
          "search": null,
          "filter": {
            "category_uid": {
              "in": null
            },
            "tour_category": {
              "eq": "5465"
            }
          },
          "pageSize": 8,
          "currentPage": 1,
          "sort": {
            "sort_order": "ASC"
          }
        }
     ```

##  **Dubai-Abu-Dhabi-Holidays Page**
-   **URL:** <https://alike.io/dubai-abu-dhabi-holidays>
-   **API:** `products`
-   This API used for **Top Attraction** section.
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/c0a857d9-0d62-4cbb-b19c-2547ab9122ed)
-   **Query:**
    ```graphql
        query products($filter: ProductAttributeFilterInput) {
          products(filter: $filter) {
            items {
              sku
              url_key
              id
              name
              tour_cities
              tour_category
              strike_price_value
              image {
                url
                __typename
              }
              price_range {
                minimum_price {
                  final_price {
                    currency
                    value
                    __typename
                  }
                  __typename
                }
                __typename
              }
              dynamicAttributes(fields: ["tour_cities", "tour_category"])
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
            "sku": {
              "in": [
                "AE-B-1901-P-0",
                "AE-B-1902-P-0",
                "AE-B-1903-P-0",
                "AE-B-1904-P-0",
                "AE-B-1905-P-0",
                "AE-V-1800-P-1",
                "AE-E-1002-P-1",
                "AE-E-1041-P-0"
              ]
            }
          }
        }
     ```

##  **Sign in Page**
-    **URL:** <https://app.alike.io/#/signin>
-    **API:** `amSocialLoginButtonConfig`
-    This API used for social login.
-    ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/78efb95a-4800-4883-8256-73159538a96e)
-    **Query:**
     ```graphql
        {
          amSocialLoginButtonConfig {
            label
            type
            url
            __typename
          }
        }
     ```
-   **API:** `requestPasswordResetEmail`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/bb2a4f97-1b2a-4f25-8fe9-caaa41d7c7c2)
-   **Query:**
     ```graphql
          mutation requestPasswordResetEmail($email: String!) {
            requestPasswordResetEmail(email: $email)
          }
      ```
-   **variables:**
    ```graphql
          {
            "email": "jay.b@7span.com"
          }
    ```

    
##  **Sign up Page**
-   **URL:** <https://app.alike.io/#/signup>
-   **API:** `createCustomerV2`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/6fb7f72f-8b73-4bf0-8208-8ba550007850)
-   **Query:**
     ```graphql
        mutation createCustomerV2($input: CustomerCreateInput!) {
          createCustomerV2(input: $input) {
            customer {
              email
              group_id
              id
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
            "is_insider": false,
            "firstname": "Firstname",
            "lastname": "Lastname",
            "email": "jay+1@alike.io",
            "password": "password"
          }
        }
     ```
     
##  **My Studio Page**
-   **URL:** <https://app.alike.io/#/my-studio/dashboard>
-   **API:** `MyDashboard`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/57a15daf-6bf8-4673-b2e7-acdb59914c76)
-   **Query:**
    ```graphql
        query MyDashboard($input: MyDashboardInput) {
          MyDashboard(input: $input) {
            earning_percentage
            goal_percenatge
            customers_count
            goal_earned_data
            goal_remain_data
            last_few_days_order_data {
              data
              xaxis
              __typename
            }
            last_few_days_profit_data {
              credit
              spent
              xaxis
              __typename
            }
            last_month_profit_data
            lifetime_sale
            revenue {
              credit
              spent
              xaxis
              __typename
            }
            sale_count
            sales_data {
              data
              xaxis
              __typename
            }
            this_month_profit_data
            total_booked_trips
            total_products
            total_revenue
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "input": {
            "from": "2-3-2024",
            "to": "1-4-2024"
          }
        }
    ```
-   **API:** `MyStudioAccount`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/84145dbf-d852-4431-bead-f8edc2a3f2de)
-   **Query:**
    ```graphql
        query MyStudioAccount($section: String!) {
          MyStudioAccount(section: $section) {
            about
            cover_photo
            name
            profile_picture
            username
            insider_username
            join_date
            __typename
          }
        }
    ```
-   **variables:**
     ```graphql
        {
          "section": "general"
        }
     ```

-   **API:** `MyDashboard` -> `top_trips`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/c2d654a1-7b1e-42d5-9945-84308bec984a)
-   **Query:**
    ```graphql
        query MyDashboard($sort: TopTripsSortInput) {
          MyDashboard {
            top_trips(sort: $sort) {
              image
              price
              revenue
              sales
              tripstory
              type_id
              __typename
            }
            __typename
          }
        }
    ```
-   **API:** `MyDashboard` -> `recent_transactions`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/9c735ca2-8e56-42fd-b58c-70592a5b02c4)
-   **Query:**
     ```graphql
        query MyDashboard($sort: RecentTransactionSortInput) {
          MyDashboard {
            recent_transactions(sort: $sort) {
              transactions {
                amount
                balance
                created_at
                transaction_type
                status
                debitCredit
                __typename
              }
              __typename
            }
            __typename
          }
        }
     ```
-   **API:** `wallets`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/9ba82770-8170-4517-ad58-a2ee1a2e1bd8)
-    **Query:**
      ```graphql
        {
          wallets {
            credit {
              balance
              currency
              __typename
            }
            __typename
          }
        }
      ```
-   **API:** `customAttributeMetadata`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/65d69019-1c17-4a0d-bb70-6c500287ff0a)
-   **Query:**
     ```graphql
        query customAttributeMetadata($attributes: [AttributeInput!]!) {
          customAttributeMetadata(attributes: $attributes) {
            items {
              attribute_options {
                label
                value
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
          "attributes": [
            {
              "attribute_code": "ins_duration",
              "entity_type": "catalog_product"
            }
          ]
        }
    ```
-   **API:** `customAttributeMetadata` for **City** selection
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/2e121a5c-e4d4-4ed8-98d3-82e9b75944f6)
-   **Query:**
     ```graphql
        query customAttributeMetadata($attributes: [AttributeInput!]!) {
          customAttributeMetadata(attributes: $attributes) {
            items {
              attribute_options {
                label
                value
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
          "attributes": [
            {
              "attribute_code": "ins_city",
              "entity_type": "catalog_product"
            }
          ]
        }
     ```
-   **API:** `MyTrips`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/d3a1a222-cc03-45f8-baaa-610451b50511)
-   **Query:**
    ```graphql
        query MyTrips($filters: MyTripsFilterInput, $search: String, $currentPage: Int!, $pageSize: Int) {
          MyTrips(
            filter: $filters
            search: $search
            currentPage: $currentPage
            pageSize: $pageSize
          ) {
            transactions {
              id
              sku
              name
              tags
              image
              price
              status
              type_id
              no_of_days
              preview_url_key
              __typename
            }
            page_info {
              current_page
              page_size
              total_pages
              __typename
            }
            total_count
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "filters": {
            "status": null,
            "type_id": null
          },
          "pageSize": 10,
          "currentPage": 1
        }
    ```
-   **API:** `Followers`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/37f0cfb1-a53c-4f58-9b66-5505babada5d)
-   **Query:**
    ```graphql
        query Followers($search: String) {
          Followers(search: $search) {
            id
            insider_id
            nick_name
            profile_picture
            __typename
          }
        }
    ```
-   **API:** `Following`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/7c50804c-2c61-4d07-884d-76e03b7dbd2b)
-   **Query:**
     ```graphql
        query Following($search: String) {
          Following(search: $search) {
            id
            insider_id
            nick_name
            profile_picture
            __typename
          }
        }
     ```
-   **API:** `CategoryImageId`
-   This API is located at **MY Profile** page
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/1342ff2b-aea5-4471-bdce-272e2e3b300c)
-   **Query:**
    ```graphql
        {
          CategoryImageId {
            attribute_id
            category_id
            category_image
            city_name
            __typename
          }
        }
     ```
-   **API:** `customAttributeMetadata`
-   This API is used when creating a trip story.
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/f5c1ba85-0821-4811-83f8-63dfd761b81e)
-   **Query:**
    ```graphql
        query customAttributeMetadata($attributes: [AttributeInput!]!) {
          customAttributeMetadata(attributes: $attributes) {
            items {
              attribute_options {
                label
                value
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
          "attributes": [
            {
              "attribute_code": "ins_tags",
              "entity_type": "catalog_product"
            }
          ]
        }
     ```
-   **API:** `customAttributeMetadata` for **Suitable for** section.
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/572768b0-5dc4-45a8-9e51-f56f2a11c8bb)
-   **Query:**
      ```graphql
        query customAttributeMetadata($attributes: [AttributeInput!]!) {
          customAttributeMetadata(attributes: $attributes) {
            items {
              attribute_options {
                label
                value
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
          "attributes": [
            {
              "attribute_code": "ins_traveller_type",
              "entity_type": "catalog_product"
            }
          ]
        }
    ```
-   **API:** `customAttributeMetadata` for **Duration** section.
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/02b261eb-83b7-458f-abfd-5ccaa4d293a6)
-   **Query:**
     ```graphql
        query customAttributeMetadata($attributes: [AttributeInput!]!) {
          customAttributeMetadata(attributes: $attributes) {
            items {
              attribute_options {
                label
                value
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
          "attributes": [
            {
              "attribute_code": "ins_duration",
              "entity_type": "catalog_product"
            }
          ]
        }
     ```
-   **API:** `CategoryImageId`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/d2fca32b-ab7d-485f-80bc-f3c7d63ccb5c)
-    This API is used for Background images.
-    **Query:**
     ```graphql
        {
          CategoryImageId {
            attribute_id
            category_id
            category_image
            city_name
            __typename
          }
        }
     ```
-   **API:** `hotel_activity_search`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/80b6606f-000a-4f46-a4c5-5a5bfb498864)
-   This API is used for hotel section.
-   **Query:**
     ```graphql
        {
          hotel_activity_search {
            city
            id
            name
            sku
            price
            strike_price
            image
            product_type
            __typename
          }
        }
    ```
-   **API:** `CreateTripStory`
-   This API is use for create trip story.
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/74f754e5-99a9-44a6-a19d-323b29607fbf)
-   **Query:**
     ```graphql
        mutation CreateTripStory($input: CreateTripStoryInput!) {
          CreateTripStory(input: $input) {
            id
            url_key
            sku
            name
            preview_url_key
            story_type
            ins_city
            short_description_alike
            ins_days
            number_of_persons
            visited_months
            ins_highlights
            ins_custom_attributes {
              ins_city
              ins_tags
              ins_traveller_type
              visited_months
              __typename
            }
            image {
              url
              __typename
            }
            price {
              minimalPrice {
                amount {
                  currency
                  value
                  __typename
                }
                __typename
              }
              __typename
            }
            ins_traveller_type
            ins_tags
            itinerary {
              image_video_itinerary {
                sub_products_image {
                  images {
                    image {
                      label
                      url
                      __typename
                    }
                    day
                    caption
                    description
                    caption
                    location
                    product_id
                    product_name
                    product_sku
                    record_id
                    sort_order
                    record_id
                    tags
                    __typename
                  }
                  option_id
                  __typename
                }
                sub_products_video {
                  videos {
                    video {
                      label
                      url
                      video_url
                      __typename
                    }
                    day
                    caption
                    description
                    caption
                    location
                    product_id
                    product_name
                    product_sku
                    record_id
                    sort_order
                    record_id
                    tags
                    __typename
                  }
                  option_id
                  __typename
                }
                __typename
              }
              trip_itinerary {
                days {
                  day
                  about
                  city
                  title
                  option_id
                  accommodation
                  sort_order
                  activities {
                    activity
                    duration
                    initialize
                    item_category
                    duration
                    product_images {
                      label
                      url
                      __typename
                    }
                    product_name
                    product_sku
                    product_id
                    website_url
                    email
                    mobile
                    product_videos {
                      label
                      url
                      video_url
                      __typename
                    }
                    record_id
                    sort_order
                    __typename
                  }
                  hotels {
                    hotel
                    duration
                    initialize
                    item_category
                    duration
                    hotel_images {
                      label
                      url
                      __typename
                    }
                    product_name
                    product_sku
                    product_id
                    hotel_videos {
                      label
                      url
                      video_url
                      __typename
                    }
                    record_id
                    sort_order
                    __typename
                  }
                  __typename
                }
                __typename
              }
              revenue {
                activity_revenue {
                  product_name
                  product_revenue
                  __typename
                }
                total
                __typename
              }
              trip_location {
                day
                city
                activity {
                  label
                  location {
                    latitude
                    longitude
                    __typename
                  }
                  sort_order
                  __typename
                }
                __typename
              }
              images {
                url
                label
                __typename
              }
              videos {
                video_url
                label
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
          "input": {
            "id": "7867",
            "type": "insider_trip_story"
          }
        }
    ```
-   **API:** `ActivitiesSerach` for **Activity** section.
-   This API is used to add activity to the trip story.
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/59d44321-4942-4121-9dc5-8f7ca10a2fdc)
-   **Query:**
     ```graphql
        query ActivitiesSerach($category_ids: [String], $type: String) {
          ActivitiesSerach(category_ids: $category_ids, type: $type) {
            id
            name
            sku
            city
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "category_ids": [
            "720",
            "721"
          ],
          "type": "attractions"
        }
    ```
-   **API:** `ActivitiesSerach` for **SIM & WIFi** section.
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/05132141-0736-4f3f-a26e-35b97c245dbf)
-   **Query:**
    ```graphql
        query ActivitiesSerach($category_ids: [String], $type: String) {
          ActivitiesSerach(category_ids: $category_ids, type: $type) {
            id
            name
            sku
            city
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "category_ids": [
            "720",
            "721"
          ],
          "type": "sim"
        }
    ```
-   **API:** `customer`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/3774b8e1-27fd-4b7e-ba3d-4fa3b820e553)
-   **Query:**
    ```query
        {
          customer {
            email
            firstname
            lastname
            profile_picture
            is_insider
            insider_id
            is_info_upadte
            username
            addresses {
              id
              default_billing
              default_shipping
              city
              company
              country_code
              postcode
              telephone
              street
              __typename
            }
            wishlists {
              id
              items_count
              __typename
            }
            __typename
          }
        }
    ```
-   **API:** `InsiderAccount`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/206da2f6-5460-463a-bb27-3e2d16a4d4da)
-   **Query:**
    ```graphql
        query InsiderAccount($username: String!) {
          InsiderAccount(username: $username) {
            social {
              label
              favicon_icon
              link
              status
              type
              sort_order
              __typename
            }
            __typename
          }
        }
    ```
-   **variables:**
     ```graphql
        {
          "username": "jay0392"
        }
     ```
-   **API:** `changeCustomerPassword`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/812b7b9b-4d92-4a79-a9d8-923be4bb508f)
-   **Query:**
    ```graphql
        mutation changeCustomerPassword($currentPassword: String!, $newPassword: String!) {
          changeCustomerPassword(
            currentPassword: $currentPassword
            newPassword: $newPassword
          ) {
            id
            email
            firstname
            lastname
            __typename
          }
        }
    ```
-   **variables:**
     ```graphql
        {
          "currentPassword": "***@123",
          "newPassword": "*****@123"
        }
    ```

##  **My Trips Page**
-   **URL:** <https://app.alike.io/#/my-trips>
-   **API:** `CategoryImageId`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/85a87c89-f4e8-4600-8497-3ff503ffa78e)
-   **Query:**
     ```graphql
        {
          CategoryImageId {
            attribute_id
            category_id
            category_image
            city_name
            __typename
          }
        }
    ```
-   **API:** `hotel_activity_search`
-   This API is used for the **Places to Stay** section on trip planner.
-   **Query:**
     ```graphql
        {
          hotel_activity_search {
            city
            id
            name
            sku
            price
            strike_price
            image
            product_type
            __typename
          }
        }
    ```
-   **API:** `CreateTripPlanner`
-   This API is used for create a trip planner.
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/7844a827-b618-4b9a-becb-b7f348a8b95d)
-   **Query:**
     ```graphql
        mutation CreateTripPlanner($input: CreateTripPlannerInput!) {
          CreateTripPlanner(input: $input) {
            id
            uid
            name
            image {
              url
              __typename
            }
            ins_days
            ins_city
            start_date
            categories {
              id
              name
              __typename
            }
            ins_custom_attributes {
              ins_city
              __typename
            }
            file_attachments {
              file_label
              record_id
              upload_file
              date
              type
              size
              __typename
            }
            travel_notes {
              is_require
              notes
              option_id
              record_id
              sort_order
              title
              type
              values {
                record_id
                sort_order
                title
                value
                __typename
              }
              __typename
            }
            trip_planner {
              customer_sharing {
                email
                name
                profile
                role
                __typename
              }
              trip_planner_data {
                days {
                  day
                  date
                  option_id
                  record_id
                  sort_order
                  cities {
                    city_name
                    about
                    city
                    option_id
                    record_id
                    sort_order
                    activities {
                      activity_image
                      notes
                      product_id
                      product_name
                      product_sku
                      duration
                      record_id
                      sort_order
                      start_time
                      end_time
                      __typename
                    }
                    food_drink {
                      activity_image
                      notes
                      product_id
                      product_name
                      product_sku
                      duration
                      record_id
                      sort_order
                      start_time
                      end_time
                      place_id
                      __typename
                    }
                    hotels {
                      activity_image
                      notes
                      product_id
                      product_name
                      product_sku
                      duration
                      record_id
                      sort_order
                      start_time
                      end_time
                      __typename
                    }
                    travel_essentials {
                      activity_image
                      notes
                      product_id
                      product_name
                      product_sku
                      duration
                      record_id
                      sort_order
                      start_time
                      end_time
                      type
                      __typename
                    }
                    __typename
                  }
                  __typename
                }
                __typename
              }
              trip_planner_location {
                activity {
                  label
                  location {
                    label
                    lat
                    latitude
                    long
                    longitude
                    __typename
                  }
                  price
                  rating
                  strike_price
                  product_image
                  sort_order
                  tour_category
                  city
                  start_time
                  end_time
                  __typename
                }
                day
                date
                __typename
              }
              trip_planner_timeline {
                activity {
                  city
                  end_time
                  label
                  record_id
                  price
                  product_image
                  sort_order
                  start_time
                  strike_price
                  tour_category
                  __typename
                }
                date
                day
                __typename
              }
              trip_planner_summary {
                count
                label
                data {
                  city
                  label
                  product_image
                  tour_category
                  date
                  start_time
                  end_time
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
-   **variables:**
    ```graphql
        {
          "input": {
            "id": "8162"
          }
        }
    ```
-   **API:** `customer` -> `wishlist_v2`
-   This API is used to wishlist.
-   Here in this API input `type` change it works like a filter.
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/2f20b1d3-d459-43af-a005-21b14590cbbf)
-   **Query:**
     ```graphql
        query customer($id: ID!, $currentPage: Int!, $pageSize: Int, $type: String, $search: String) {
          customer {
            wishlist_v2(id: $id) {
              id
              items_count
              total_count
              items_v2(
                currentPage: $currentPage
                pageSize: $pageSize
                type: $type
                search: $search
              ) {
                page_info {
                  current_page
                  page_size
                  total_pages
                  __typename
                }
                items {
                  id
                  product {
                    id
                    uid
                    name
                    sku
                    strike_price_value
                    type
                    image {
                      url
                      __typename
                    }
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
                    dynamicAttributes(fields: ["tour_cities", "tour_category", "id"])
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
          "id": "13144",
          "currentPage": 1,
          "pageSize": 300,
          "type": "hotels"
        }
      ```
-   **API:** `tripPlannerActivitiesSerach`
-   This API is similar to wishlist_v2 GraphQl just different is in this API load all product whech we passed type as filter.
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/a131c9b3-22e6-4707-a08b-058453ebaffe)
-   **Query:**
     ```graphql
        query tripPlannerActivitiesSerach($category_ids: [String], $type: String!) {
          tripPlannerActivitiesSerach(category_ids: $category_ids, type: $type) {
            city
            id
            name
            sku
            price
            strike_price
            image
            product_type
            __typename
          }
        }
    ```
-   **variables:**
   ```graphql
        {
          "category_ids": "720",
          "type": "things_to_do"
        }
   ```
-   **API:** `CreateTripPlanner` -> `travel_notes`
-   Here this API used for **Notes & Files** section.
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/a1d0a40d-4fcb-4bd0-af54-5c185f2b9b3d)
-   **Query:**
     ```graphql
        mutation CreateTripPlanner($input: CreateTripPlannerInput!) {
          CreateTripPlanner(input: $input) {
            id
            uid
            name
            image {
              url
              __typename
            }
            ins_days
            ins_city
            start_date
            categories {
              id
              name
              __typename
            }
            ins_custom_attributes {
              ins_city
              __typename
            }
            file_attachments {
              file_label
              record_id
              upload_file
              date
              type
              size
              __typename
            }
            travel_notes {
              is_require
              notes
              option_id
              record_id
              sort_order
              title
              type
              values {
                record_id
                sort_order
                title
                value
                __typename
              }
              __typename
            }
            trip_planner {
              customer_sharing {
                email
                name
                profile
                role
                __typename
              }
              trip_planner_data {
                days {
                  day
                  date
                  option_id
                  record_id
                  sort_order
                  cities {
                    city_name
                    about
                    city
                    option_id
                    record_id
                    sort_order
                    activities {
                      activity_image
                      notes
                      product_id
                      product_name
                      product_sku
                      duration
                      record_id
                      sort_order
                      start_time
                      end_time
                      __typename
                    }
                    food_drink {
                      activity_image
                      notes
                      product_id
                      product_name
                      product_sku
                      duration
                      record_id
                      sort_order
                      start_time
                      end_time
                      place_id
                      __typename
                    }
                    hotels {
                      activity_image
                      notes
                      product_id
                      product_name
                      product_sku
                      duration
                      record_id
                      sort_order
                      start_time
                      end_time
                      __typename
                    }
                    travel_essentials {
                      activity_image
                      notes
                      product_id
                      product_name
                      product_sku
                      duration
                      record_id
                      sort_order
                      start_time
                      end_time
                      type
                      __typename
                    }
                    __typename
                  }
                  __typename
                }
                __typename
              }
              trip_planner_location {
                activity {
                  label
                  location {
                    label
                    lat
                    latitude
                    long
                    longitude
                    __typename
                  }
                  price
                  rating
                  strike_price
                  product_image
                  sort_order
                  tour_category
                  city
                  start_time
                  end_time
                  __typename
                }
                day
                date
                __typename
              }
              trip_planner_timeline {
                activity {
                  city
                  end_time
                  label
                  record_id
                  price
                  product_image
                  sort_order
                  start_time
                  strike_price
                  tour_category
                  __typename
                }
                date
                day
                __typename
              }
              trip_planner_summary {
                count
                label
                data {
                  city
                  label
                  product_image
                  tour_category
                  date
                  start_time
                  end_time
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
-   **variables:**
     ```graphql
        {
          "input": {
            "id": 8162,
            "name": "dubai",
            "banner_image": {
              "base64": null,
              "status": "completed",
              "url": "https://alike-asset.s3.eu-central-1.amazonaws.com/catalog/product/placeholder/default/trip-placeholder.jpg"
            },
            "category_id": [
              "720"
            ],
            "ins_city": [
              "720"
            ],
            "ins_days": "3",
            "sku": null,
            "start_date": "2024-04-02 00:00:00",
            "travel_notes": [
              {
                "option_id": "211c1e0b83b9c69fa9c4bdede203c1e3",
                "record_id": "211c1e0b83b9c69fa9c4bdede203c1e3",
                "is_require": true,
                "notes": "<p>dfsafds</p>",
                "sort_order": 1,
                "title": "abc",
                "type": "area",
                "values": []
              },
              {
                "option_id": "861dc9bd7f4e7dd3cccd534d0ae2a2e9",
                "record_id": "861dc9bd7f4e7dd3cccd534d0ae2a2e9",
                "is_require": true,
                "notes": null,
                "sort_order": 2,
                "title": null,
                "type": "area",
                "values": []
              }
            ],
            "file_attachments": [],
            "trip_planner_itinerary": [
              {
                "day": "1",
                "date": "2024-04-02T06:59:10.221Z",
                "option_id": "6e79ed05baec2754e25b4eac73a332d2",
                "record_id": "6e79ed05baec2754e25b4eac73a332d2",
                "sort_order": "1",
                "cities": [
                  {
                    "about": null,
                    "city": "720",
                    "option_id": "7e448ed9dd44e6e22442dac8e21856ae",
                    "record_id": "7e448ed9dd44e6e22442dac8e21856ae",
                    "sort_order": null,
                    "activities": [
                      {
                        "notes": null,
                        "product_id": "34",
                        "product_sku": "AE-E-1033-P-0",
                        "duration": null,
                        "record_id": "24368c745de15b3d2d6279667debcba3",
                        "sort_order": 1,
                        "start_time": null,
                        "end_time": null,
                        "type": "activity",
                        "product_name": "Desert Safari",
                        "activity_image": "https://alike-asset.s3.eu-central-1.amazonaws.com/catalog/product/b/a/base-image.jpg?store=alike&image-type=image"
                      }
                    ],
                    "food_drink": [],
                    "hotels": [],
                    "travel_essentials": []
                  }
                ]
              },
              {
                "day": "2",
                "date": "2024-04-03T06:59:10.221Z",
                "option_id": "fa2e8c4385712f9a1d24c363a2cbe5b8",
                "record_id": "fa2e8c4385712f9a1d24c363a2cbe5b8",
                "sort_order": "2",
                "cities": [
                  {
                    "about": null,
                    "city": "720",
                    "option_id": "b31df16a88ce00fed951f24b46e08649",
                    "record_id": "b31df16a88ce00fed951f24b46e08649",
                    "sort_order": null,
                    "activities": [],
                    "food_drink": [],
                    "hotels": [],
                    "travel_essentials": []
                  }
                ]
              },
              {
                "day": "3",
                "date": "2024-04-04T06:59:10.221Z",
                "option_id": "14678db82874f1456031fcc05a3afaf6",
                "record_id": "14678db82874f1456031fcc05a3afaf6",
                "sort_order": "3",
                "cities": [
                  {
                    "about": null,
                    "city": "720",
                    "option_id": "7ab6acc5bbf252028d5ffa1b92e6beb1",
                    "record_id": "7ab6acc5bbf252028d5ffa1b92e6beb1",
                    "sort_order": null,
                    "activities": [],
                    "food_drink": [],
                    "hotels": [],
                    "travel_essentials": []
                  }
                ]
              }
            ]
          }
        }
     ```
-    **API:** `customer` -> `wishlist_v2`
-    Here this GraphQl show all product which user add on bucket.
-    ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/b4dc4765-edb1-4dc1-9bf7-1fa7137cc885)
-    **Query:**
     ```graphql
        query customer($id: ID!, $currentPage: Int!, $pageSize: Int, $type: String, $search: String) {
          customer {
            wishlist_v2(id: $id) {
              id
              items_count
              total_count
              items_v2(
                currentPage: $currentPage
                pageSize: $pageSize
                type: $type
                search: $search
              ) {
                page_info {
                  current_page
                  page_size
                  total_pages
                  __typename
                }
                items {
                  id
                  product {
                    id
                    uid
                    name
                    sku
                    strike_price_value
                    type
                    image {
                      url
                      __typename
                    }
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
                    dynamicAttributes(fields: ["tour_cities", "tour_category", "id"])
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
          "pageSize": 8,
          "currentPage": 1,
          "id": "13144"
        }
     ```

-    **API** `customer` ->`wishlist_v2` (used for search)
-    ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/29961d51-744c-4d9a-9a93-5e6fdfb2a2fb)
-    **Query:**
     ```graphql
        query customer($id: ID!, $currentPage: Int!, $pageSize: Int, $type: String, $search: String) {
          customer {
            wishlist_v2(id: $id) {
              id
              items_count
              total_count
              items_v2(
                currentPage: $currentPage
                pageSize: $pageSize
                type: $type
                search: $search
              ) {
                page_info {
                  current_page
                  page_size
                  total_pages
                  __typename
                }
                items {
                  id
                  product {
                    id
                    uid
                    name
                    sku
                    strike_price_value
                    type
                    image {
                      url
                      __typename
                    }
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
                    dynamicAttributes(fields: ["tour_cities", "tour_category", "id"])
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
      ```qraphql
        {
          "search": "dub",
          "pageSize": 8,
          "currentPage": 1,
          "id": "13144"
        }
     ```
-    **API:** `tripPlannerCollection`
-    ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/bf03f784-c5a0-4961-b378-e2758d1a1176)
-    **Query:**
     ```graphql
        query tripPlannerCollection($filters: TripPlannerCollectionFilter, $search: String, $currentPage: Int!, $pageSize: Int) {
          tripPlannerCollection(
            filter: $filters
            search: $search
            currentPage: $currentPage
            pageSize: $pageSize
          ) {
            page_info {
              current_page
              page_size
              total_pages
              __typename
            }
            total_count
            trip_planner {
              base_image
              customer_sharing {
                email
                name
                profile
                role
                __typename
              }
              id
              ins_duration
              name
              start_date
              __typename
            }
            __typename
          }
        }
     ```
-   **variables:**
    ```graphql
        {
          "filters": {
            "type": "upcoming"
          },
          "pageSize": 8,
          "currentPage": 1
        }
    ```
    
##  **Trip Stories Page**
-   **URL:** <https://alike.io/trip-stories?utm_source=site&utm_medium=menu-desktop&utm_campaign=menu>
-   **API:** `products`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/f320b815-9089-4dc5-802a-5343ca1cb91e)
-   **Query:**
     ```graphql
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
              id
              url_key
              product_likes
              ins_days
              name
              short_description_alike
              ins_tags
              ins_city
              story_icons_count
              icons {
                icon_url
                label
                count
                __typename
              }
              dynamicAttributes(fields: ["ins_tags", "ins_city"])
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
              image {
                url
                __typename
              }
              small_image {
                url
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
          "currentPage": 1,
          "pageSize": 6,
          "search": "",
          "filter": {
            "category_id": {
              "eq": "722"
            },
            "ins_city": {
              "in": []
            },
            "ins_traveller_type": {
              "in": []
            },
            "ins_tags": {
              "in": []
            },
            "insider_approval": {
              "eq": "2"
            },
            "insider_id": {},
            "item_category": {
              "in": [
                "7"
              ]
            },
            "ins_days": {
              "in": []
            },
            "type_id": {
              "in": []
            }
          },
          "sort": {}
        }
    ```

##  **Trip Storie Detail Page**
-   **URL:** <https://alike.io/trip-stories/dubai-delights-3-day-itinerary-pre-arrival>
-   **API:** `products`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/cf85380f-64e3-4849-8ca8-16f18e25a2a5)
-   **Query:**
    ```graphql
        query products($search: String, $filter: ProductAttributeFilterInput) {
          products(search: $search, filter: $filter) {
            items {
              id
              url_key
              base_video
              description {
                html
                __typename
              }
              image {
                url
                __typename
              }
              number_of_persons
              name
              ins_city
              ins_city_image
              product_likes
              ins_days
              short_description_alike
              ins_tags
              is_liked
              ins_highlights
              insider_data {
                followers
                insider_name
                insider_logo
                insider_id
                is_followed
                username
                cover_image
                __typename
              }
              ins_traveller_type
              sku
              story_type
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
              itinerary {
                image_video_itinerary {
                  sub_products_image {
                    images {
                      image {
                        label
                        url
                        __typename
                      }
                      day
                      caption
                      description
                      caption
                      location
                      product_id
                      product_name
                      product_sku
                      record_id
                      sort_order
                      record_id
                      tags
                      __typename
                    }
                    option_id
                    __typename
                  }
                  sub_products_video {
                    videos {
                      video {
                        label
                        url
                        video_url
                        __typename
                      }
                      day
                      caption
                      description
                      caption
                      location
                      product_id
                      product_name
                      product_sku
                      record_id
                      sort_order
                      record_id
                      tags
                      __typename
                    }
                    option_id
                    __typename
                  }
                  __typename
                }
                videos {
                  caption
                  url
                  label
                  day
                  product_name
                  price
                  location
                  video_url
                  icon_url
                  __typename
                }
                images {
                  url
                  label
                  day
                  product_name
                  price
                  location
                  __typename
                }
                trip_itinerary {
                  days {
                    day
                    title
                    about
                    option_id
                    initialize
                    record_id
                    is_available
                    sort_order
                    accommodation
                    city
                    city_name
                    city_image_url
                    activities {
                      activity
                      api_connected
                      product_sku
                      product_name
                      product_url
                      product_id
                      initialize
                      record_id
                      sort_order
                      activity_description
                      activity_price
                      item_category
                      icon_url
                      duration
                      activity_image
                      attribute_set_id
                      location
                      product_images {
                        url
                        label
                        __typename
                      }
                      product_videos {
                        video_url
                        url
                        label
                        __typename
                      }
                      __typename
                    }
                    hotels {
                      hotel
                      product_sku
                      product_name
                      product_url
                      product_id
                      initialize
                      record_id
                      sort_order
                      hotel_description
                      location
                      hotel_price
                      item_category
                      icon_url
                      duration
                      hotel_image
                      attribute_set_id
                      hotel_images {
                        url
                        label
                        __typename
                      }
                      hotel_videos {
                        video_url
                        url
                        label
                        __typename
                      }
                      __typename
                    }
                    __typename
                  }
                  __typename
                }
                trip_location {
                  day
                  activity {
                    location {
                      latitude
                      longitude
                      __typename
                    }
                    label
                    sort_order
                    duration
                    price
                    __typename
                  }
                  __typename
                }
                __typename
              }
              story_icons_count
              icons {
                icon_url
                label
                count
                __typename
              }
              dynamicAttributes(fields: ["ins_traveller_type", "visited_months", "ins_tags"])
              media_gallery {
                url
                label
                __typename
                ... on ProductVideo {
                  video_content {
                    media_type
                    video_provider
                    video_url
                    video_title
                    video_description
                    video_metadata
                    __typename
                  }
                  __typename
                }
              }
              __typename
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
-   **variables:**
     ```graphql
        {
          "filter": {
            "url_key": {
              "eq": "dubai-delights-3-day-itinerary-pre-arrival"
            }
          },
          "pageSize": 1,
          "currentPage": 1
        }
     ```
-   **API:** `products` -> `product_comment`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/72c63a44-b452-4e69-8fab-5f946b8ea347)
-   **Query:**
    ```graphql
           query products($filter: ProductAttributeFilterInput, $currentPage: Int, $pageSize: Int) {
          products(filter: $filter) {
            items {
              product_comment(currentPage: $currentPage, pageSize: $pageSize) {
                page_info {
                  current_page
                  page_size
                  total_pages
                  __typename
                }
                total_count
                comments {
                  comment
                  customer_photo
                  date
                  username
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
-   **variables:**
    ```graphql
        {
          "currentPage": 1,
          "pageSize": 10,
          "filter": {
            "url_key": {
              "eq": "dubai-delights-3-day-itinerary-pre-arrival"
            }
          }
        }
    ```
-   **API:** `CategoryImageId`
-   **Query:**
     ```graphql
        {
          CategoryImageId {
            attribute_id
            category_id
            category_image
            city_name
            __typename
          }
        }
     ```
-   **API:** `products`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/f95a942c-c935-4571-8536-a2f577add73b)
-   **Query:**
     ```graphql
        query products($search: String, $filter: ProductAttributeFilterInput) {
          products(search: $search, filter: $filter) {
            items {
              id
              url_key
              base_video
              description {
                html
                __typename
              }
              image {
                url
                __typename
              }
              number_of_persons
              name
              ins_city
              ins_city_image
              product_likes
              ins_days
              short_description_alike
              ins_tags
              is_liked
              ins_highlights
              insider_data {
                followers
                insider_name
                insider_logo
                insider_id
                is_followed
                username
                cover_image
                __typename
              }
              ins_traveller_type
              sku
              story_type
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
              itinerary {
                image_video_itinerary {
                  sub_products_image {
                    images {
                      image {
                        label
                        url
                        __typename
                      }
                      day
                      caption
                      description
                      caption
                      location
                      product_id
                      product_name
                      product_sku
                      record_id
                      sort_order
                      record_id
                      tags
                      __typename
                    }
                    option_id
                    __typename
                  }
                  sub_products_video {
                    videos {
                      video {
                        label
                        url
                        video_url
                        __typename
                      }
                      day
                      caption
                      description
                      caption
                      location
                      product_id
                      product_name
                      product_sku
                      record_id
                      sort_order
                      record_id
                      tags
                      __typename
                    }
                    option_id
                    __typename
                  }
                  __typename
                }
                videos {
                  caption
                  url
                  label
                  day
                  product_name
                  price
                  location
                  video_url
                  icon_url
                  __typename
                }
                images {
                  url
                  label
                  day
                  product_name
                  price
                  location
                  __typename
                }
                trip_itinerary {
                  days {
                    day
                    title
                    about
                    option_id
                    initialize
                    record_id
                    is_available
                    sort_order
                    accommodation
                    city
                    city_name
                    city_image_url
                    activities {
                      activity
                      api_connected
                      product_sku
                      product_name
                      product_url
                      product_id
                      initialize
                      record_id
                      sort_order
                      activity_description
                      activity_price
                      item_category
                      icon_url
                      duration
                      activity_image
                      attribute_set_id
                      location
                      product_images {
                        url
                        label
                        __typename
                      }
                      product_videos {
                        video_url
                        url
                        label
                        __typename
                      }
                      __typename
                    }
                    hotels {
                      hotel
                      product_sku
                      product_name
                      product_url
                      product_id
                      initialize
                      record_id
                      sort_order
                      hotel_description
                      location
                      hotel_price
                      item_category
                      icon_url
                      duration
                      hotel_image
                      attribute_set_id
                      hotel_images {
                        url
                        label
                        __typename
                      }
                      hotel_videos {
                        video_url
                        url
                        label
                        __typename
                      }
                      __typename
                    }
                    __typename
                  }
                  __typename
                }
                trip_location {
                  day
                  activity {
                    location {
                      latitude
                      longitude
                      __typename
                    }
                    label
                    sort_order
                    duration
                    price
                    __typename
                  }
                  __typename
                }
                __typename
              }
              story_icons_count
              icons {
                icon_url
                label
                count
                __typename
              }
              dynamicAttributes(fields: ["ins_traveller_type", "visited_months", "ins_tags"])
              media_gallery {
                url
                label
                __typename
                ... on ProductVideo {
                  video_content {
                    media_type
                    video_provider
                    video_url
                    video_title
                    video_description
                    video_metadata
                    __typename
                  }
                  __typename
                }
              }
              __typename
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
     ```garphql
        {
          "filter": {
            "url_key": {
              "eq": "travelosaur-dubai-delights-5-days-of-thrills-culture-and-magi"
            }
          },
          "pageSize": 1,
          "currentPage": 1
        }
     ```
-   **API:** `insiderTickets`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/97a8dcee-0d9a-4ac5-8bb6-3e40e1fe7c3d)
-   **Query:**
     ```graphql
        mutation ($input: InsiderTicketInput!) {
          insiderTickets(input: $input) {
            data {
              age
              hide_adult
              hide_child
              hide_infant
              adult_label
              tickets {
                exp_excluded
                id
                label
                optionDescription
                adultPrice
                childPrice
                infantPrice
                transfer_types {
                  code
                  id
                  label
                  __typename
                }
                __typename
              }
              type
              __typename
            }
            error
            success
            __typename
          }
        }
     ```
-   **variables:**
     ```graphql
        {
          "input": {
            "itinerary_id": 7651,
            "product_id": 2431,
            "date": "02/04/2024"
          }
        }
     ```
-   **API:** `itineraryPrice`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/631a94d1-a7b0-4e57-bf8e-187033550285)
-   **Query:**
    ```graphql
        mutation ($input: ItineraryPriceInput!) {
          itineraryPrice(input: $input) {
            data {
              actual_price
              adult_price
              child_price
              adult_qty
              child_qty
              qty
              saved_price
              special_price
              type
              timeslots {
                available
                event_id
                id
                label
                start_time
                total
                used
                __typename
              }
              __typename
            }
            error
            success
            __typename
          }
        }
    ```
-   **variables:**]
     ```graphql
        {
          "input": {
            "itinerary_id": 7651,
            "product_id": 2431,
            "date": "02/04/2024",
            "qty": 1,
            "ticket_id": "e3e9602ef57d2ddd50d0abaa98d2a6a6",
            "transfer_id": "no_transfer",
            "adult_qty": 1,
            "child_qty": 1,
            "pickup_address": ""
          }
        }
     ```
-   **API:** `storeConfig`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/7fcbdecb-4649-47f5-a38c-075ae92658dc)
-   **Query:**
    ```graphql
        {
          storeConfig {
            custom_general_rental_price
            custom_general_rental_free
            __typename
          }
        }
    ```

##  **Cart Page**
-   **URL:** <https://alike.io/cart>
-   **API:** `addActivityProductsToCart`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/a1cb20be-cca7-4096-8b5c-90a69047eda6)
-   **Query:**
    ```graphql
         mutation ($cartId: String!, $cartItems: [ActivityCartItemInput!]!) {
          addActivityProductsToCart(cartId: $cartId, cartItems: $cartItems) {
            cart {
              prices {
                grand_total {
                  currency
                  value
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
-   **variables:**
     ```graphql
        {
          "cartId": "aM2BXkeToWfsAqnbqe8fF3T0EBk6I7MT",
          "cartItems": [
            {
              "insider": true,
              "itinerary_id": 7651,
              "product_id": 2431,
              "ticket_id": "e3e9602ef57d2ddd50d0abaa98d2a6a6",
              "ticket_label": "30 Days Tourist Visa",
              "date": "2024/04/02",
              "qty": 1,
              "timeslot_info": null,
              "adult_qty": 1,
              "child_qty": 0,
              "transfer_id": "no_transfer",
              "pickup_address": ""
            }
          ]
        }
     ```
-   **API:** `addProductToCart`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/8b7dd01a-060e-445f-9fbf-d97be852a054)
-   **Query:**
    ```graphql
        mutation ($cartId: String!, $cartItems: [ProductToCartInput!]!) {
          addProductToCart(cartId: $cartId, cartItems: $cartItems) {
            cart {
              prices {
                grand_total {
                  currency
                  value
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
-   **variables:**
     ```graphql
        {
          "cartId": "aM2BXkeToWfsAqnbqe8fF3T0EBk6I7MT",
          "cartItems": [
            {
              "product_id": 1995,
              "qty": 1,
              "additional_options": {
                "tour_date": "",
                "start_from": "2024/04/05",
                "rental_days": 0
              }
            }
          ]
        }
     ```
-    **API:** `cart`
-    ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/b77ab05d-43a7-4554-adb6-179f29bb66fa)
-    **Query:**
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
-    **variables:**
     ```graphql
        {
          "cart_id": "aM2BXkeToWfsAqnbqe8fF3T0EBk6I7MT"
        }
     ```
-   **API:** `setShippingAddressesOnCart`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/3470d880-7d38-474b-ba01-db8ec9c228cb)
-   **Query:**
    ```graphql
        mutation ($input: SetShippingAddressesOnCartInput!) {
          setShippingAddressesOnCart(input: $input) {
            cart {
              shipping_addresses {
                firstname
                lastname
                company
                street
                city
                region {
                  code
                  label
                  __typename
                }
                postcode
                telephone
                country {
                  code
                  label
                  __typename
                }
                available_shipping_methods {
                  carrier_code
                  carrier_title
                  method_code
                  method_title
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
-   **variables:**
    ```graphql
        {
          "input": {
            "cart_id": "aM2BXkeToWfsAqnbqe8fF3T0EBk6I7MT",
            "shipping_addresses": [
              {
                "address": {
                  "firstname": "test",
                  "lastname": "test",
                  "company": "",
                  "street": [
                    "Digital Sale"
                  ],
                  "city": "Digital Sale",
                  "region": "test",
                  "region_id": 0,
                  "postcode": "12345",
                  "telephone": "2025550114",
                  "save_in_address_book": false,
                  "mobile_country_code": "US",
                  "country_code": "US"
                }
              }
            ]
          }
        }
    ```
-    **API:** `abandonedCartCapture`
-    ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/20bf6bbd-1ea8-4a9d-8d92-76c6ae75df4d)
-    **Query:**
     ```graphql
        mutation ($input: AbandonedCartInput!) {
          abandonedCartCapture(input: $input) {
            status
            __typename
          }
        }
     ```
-   **variables:**
     ```graphql
        {
          "input": {
            "cart_id": "aM2BXkeToWfsAqnbqe8fF3T0EBk6I7MT",
            "email": "jay@alike.io",
            "name": "jay"
          }
        }
     ```
-   **API:** `setGuestEmailOnCart`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/193c793d-af77-4ac6-bf30-2e3a15cca077)
-   **Query:**
    ```graphql
        mutation ($input: SetGuestEmailOnCartInput) {
          setGuestEmailOnCart(input: $input) {
            cart {
              email
              __typename
            }
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "input": {
            "cart_id": "aM2BXkeToWfsAqnbqe8fF3T0EBk6I7MT",
            "email": "jay@alike.io"
          }
        }
    ```
-   **API:** `setBillingAddressOnCart`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/def9a842-c8ac-448f-aff0-d8067d4eef64)
-   **Query:**
     ```graphql
        mutation ($input: SetBillingAddressOnCartInput!) {
          setBillingAddressOnCart(input: $input) {
            cart {
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
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "input": {
            "cart_id": "aM2BXkeToWfsAqnbqe8fF3T0EBk6I7MT",
            "billing_address": {
              "address": {
                "firstname": "jay",
                "lastname": "bhuva",
                "company": "",
                "street": [
                  "Digital Sale"
                ],
                "city": "Digital Sale",
                "region": "test",
                "region_id": 0,
                "postcode": "12345",
                "telephone": "+91 83838 38383",
                "save_in_address_book": true,
                "mobile_country_code": "IN",
                "country_code": "IN"
              },
              "hotel_remarks": ""
            }
          }
        }
    ```
-   **API:** `popularOffers`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/e2b8de22-dbbe-48ef-91ad-afa4efcb50d1)
-   **Query:**
     ```graphql
        {
          popularOffers {
            badgeText
            coupon
            description
            shortDescription
            termsAndConditions
            title
            __typename
          }
        }
    ```
-   **API:** `placeOrder`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/bf772254-5cae-4330-926e-b62127676418)
-   **Query:**
    ```graphql
        mutation ($input: PlaceOrderInput!) {
          placeOrder(input: $input) {
            order {
              order_number
              __typename
            }
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "input": {
            "cart_id": "aM2BXkeToWfsAqnbqe8fF3T0EBk6I7MT",
            "guest_email_confirm": false
          }
        }
    ```
-   **API:** `placeRazorpayOrder`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/ed6836d5-8a9c-4704-bfc7-12ef040a279d)
-   **Query:**
    ```graphql
        mutation ($orderId: String) {
          placeRazorpayOrder(order_id: $orderId) {
            success
            rzp_order_id
            order_id
            amount
            currency
            message
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "orderId": "1051786"
        }
    ```

##  **JCB Page**
-   **URL:** <https://alike.io/jcb>
-   **API:** `passProducts`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/4e062059-1904-4f2d-83f4-045d34e7a6dd)
-   **Query:**
     ```graphql
        query passProducts($uid: String!) {
          passProducts(uid: $uid) {
            items {
              uid
              id
              url_key
              name
              image {
                url
                __typename
              }
              thumbnail {
                url
                __typename
              }
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
              sku
              adult_price
              child_price
              pass_adult_price
              pass_child_price
              pass_discount_label
              pass_display_price
              pass_variation_id
              pass_variation_name
              __typename
            }
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "uid": "ODAwNg=="
        }
    ```
-   **API:** `passPremium`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/4cbc0154-c3ea-4a36-9e9a-9379992970a8)
-   **Query:**
     ```graphql
        query passPremium($uid: String!) {
          passPremium(uid: $uid) {
            items {
              uid
              id
              url_key
              name
              image {
                url
                __typename
              }
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
              sku
              adult_price
              child_price
              pass_adult_price
              pass_child_price
              pass_discount_label
              pass_display_price
              pass_variation_id
              pass_variation_name
              __typename
            }
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "uid": "ODAwNg=="
        }
    ```
-   **API:** `passTravel`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/e845ecd7-7c63-4eea-9703-d42d7176ac2a)
-   **Query:**
     ```graphql
        query passTravel($uid: String!) {
          passTravel(uid: $uid) {
            items {
              uid
              id
              url_key
              name
              image {
                url
                __typename
              }
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
              sku
              adult_price
              child_price
              pass_adult_price
              pass_child_price
              pass_discount_label
              pass_display_price
              pass_variation_id
              pass_variation_name
              __typename
            }
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "uid": "ODAwNg=="
        }
    ```

##  **About Insider Page**
-   ***URL:** <https://alike.io/trawheeling>
-   **API:** `InsiderAccount`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/e2f66080-f9d6-43b1-a653-4804725e9fc4)
-   **Query:**
    ```graphql
        query InsiderAccount($username: String!) {
          InsiderAccount(username: $username) {
            cover_photo
            social {
              label
              favicon_icon
              link
              status
              type
              sort_order
              __typename
            }
            visited_cities {
              name
              url_key
              __typename
            }
            followers
            following
            is_followed
            about
            city
            join_date
            name
            profile_picture
            username
            insider_id
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "username": "trawheeling"
        }
    ```
-   **API:** `CategoryImageId`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/5c8cbd79-78f4-419a-99fe-15dcc3e2b978)
-   **Query:**
    ```graphql
        {
          CategoryImageId {
            attribute_id
            category_id
            category_image
            city_name
            __typename
          }
        }
    ```

##  **Travel pass Detail Page**
-   **URL:** <https://alike.io/products/the-london-passr>
-   **API:** `products`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/07d83042-94e6-4312-90a9-ec58cc1bb3ba)
-   **Query:**
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
-   **variables:**
    ```graphql
        {
          "filter": {
            "url_key": {
              "eq": "the-london-passr"
            }
          },
          "pageSize": 1,
          "currentPage": 1
        }
    ```
-   **API:** `getMusementActivity`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/84fca3e2-be42-4c99-8a5c-3fb74a797cd4)
-   **Query:**
    ```graphql
        query getMusementActivity($input: MusementActivityInput) {
          getMusementActivity(input: $input) {
            booking_type
            daily
            open
            order_box_elements
            sold_out
            uuid
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "input": {
            "activity_uuid": "0f636ca4-2046-11e7-9cc9-06a7e332783f",
            "pickup": ""
          }
        }
    ```
-   **API:** `getMusementActivityDates`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/9534014f-bb78-446a-8424-ca7d442926ba)
-   **Query:**
    ```graphql
        query getMusementActivityDates($input: MusementActivityDatesInput) {
          getMusementActivityDates(input: $input) {
            day
            price
            sold_out
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "input": {
            "activity_uuid": "0f636ca4-2046-11e7-9cc9-06a7e332783f",
            "pickup": "",
            "booking_type": "NO-CALENDAR-FIXED-VALIDITY",
            "date_from": "",
            "date_to": ""
          }
        }
    ```
-   **API:** `getMusementTickets`
-   ![image](https://github.com/jay-b-7span/Alike_Document/assets/114227263/d8a71c7e-d049-4dc3-a106-fcc728d90d7f)
-   **Query:**
     ```graphql
        query getMusementTickets($input: MusementActivityInput) {
          getMusementTickets(input: $input) {
            groups {
              default
              feature_code
              name
              slots {
                languages {
                  code
                  name
                  __typename
                }
                products {
                  activity_uuid
                  default
                  discount_amount {
                    currency
                    formatted_iso_value
                    formatted_value
                    value
                    __typename
                  }
                  holder_code
                  holder_code_normalized
                  max_buy
                  merchant_price {
                    currency
                    formatted_iso_value
                    formatted_value
                    value
                    __typename
                  }
                  min_buy
                  name
                  original_retail_price {
                    currency
                    formatted_iso_value
                    formatted_value
                    value
                    __typename
                  }
                  original_retail_price_without_service_fee {
                    currency
                    formatted_iso_value
                    formatted_value
                    value
                    __typename
                  }
                  product_id
                  retail_price {
                    currency
                    formatted_iso_value
                    formatted_value
                    value
                    __typename
                  }
                  retail_price_without_service_fee {
                    currency
                    formatted_iso_value
                    formatted_value
                    value
                    __typename
                  }
                  service_fee {
                    currency
                    formatted_iso_value
                    formatted_value
                    value
                    __typename
                  }
                  type
                  __typename
                }
                tag
                time
                __typename
              }
              type
              __typename
            }
            __typename
          }
        }
    ```
-   **variables:**
    ```graphql
        {
          "input": {
            "product_id": 360,
            "activity_uuid": "0f636ca4-2046-11e7-9cc9-06a7e332783f",
            "pickup": "",
            "day": null,
            "booking_type": "NO-CALENDAR-FIXED-VALIDITY"
          }
        }
    ```
