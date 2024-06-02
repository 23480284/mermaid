<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ER Diagram with Mermaid.js</title>
    <script type="module">
        import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
        mermaid.initialize({ startOnLoad: true });
    </script>
</head>
<body>
    <div class="mermaid">
        erDiagram
            CUSTOMER {
                int customer_id
                int store_id
                string first_name
                string last_name
                string email
                boolean activebool
                int address_id
                date create_date
                date last_update
                boolean active
            }
            ADDRESS {
                int address_id
                string address
                string address2
                string district
                int city_id
                string postal_code
                string phone
                date last_update
            }
            CITY {
                int city_id
                string city
                int country_id
                date last_update
            }
            COUNTRY {
                int country_id
                string country
                date last_update
            }
            STORE {
                int store_id
                int manager_staff_id
                int address_id
                date last_update
            }
            STAFF {
                int staff_id
                string first_name
                string last_name
                string email
                int address_id
                int store_id
                boolean active
                string username
                string password
                date last_update
                string picture
            }
            PAYMENT {
                int payment_id
                int customer_id
                int staff_id
                int rental_id
                float amount
                date payment_date
            }
            RENTAL {
                int rental_id
                date rental_date
                int inventory_id
                int customer_id
                date return_date
                int staff_id
                date last_update
            }
            INVENTORY {
                int inventory_id
                int film_id
                int store_id
                date last_update
            }
            FILM {
                int film_id
                string title
                string description
                int release_year
                int language_id
                int rental_duration
                float rental_rate
                int length
                float replacement_cost
                string rating
                date last_update
                string special_features
                text fulltext
            }
            LANGUAGE {
                int language_id
                string name
                date last_update
            }
            ACTOR {
                int actor_id
                string first_name
                string last_name
                date last_update
            }
            FILM_ACTOR {
                int actor_id
                int film_id
                date last_update
            }
            CATEGORY {
                int category_id
                string name
                date last_update
            }
            FILM_CATEGORY {
                int film_id
                int category_id
                date last_update
            }

            CUSTOMER ||--o{ RENTAL : has
            RENTAL ||--|{ PAYMENT : includes
            CUSTOMER }|..|{ ADDRESS : uses
            ADDRESS ||--o{ CITY : located_in
            CITY ||--o{ COUNTRY : part_of
            STORE ||--o{ STAFF : employs
            STORE ||--o{ INVENTORY : stocks
            STAFF ||--o{ PAYMENT : processes
            INVENTORY ||--o{ RENTAL : rented_as
            FILM ||--o{ INVENTORY : included_in
            FILM ||--|{ FILM_CATEGORY : categorized_as
            FILM ||--|{ FILM_ACTOR : includes
            ACTOR ||--|{ FILM_ACTOR : acts_in
            CATEGORY ||--|{ FILM_CATEGORY : groups
            FILM ||--o{ LANGUAGE : in_language
    </div>
</body>
</html>
