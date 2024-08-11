# 🌳 Ecolaura Database Schema: Rooting Our Sustainable Data



Welcome to Ecolaura's Database Schema documentation! Just as a forest's root system forms an intricate network supporting life above ground, our database schema provides the foundation for our sustainable e-commerce platform. Let's explore the structure of our digital soil! 🌿🗃️



## 🌍 Overview



Our database design philosophy is centered around:

- Efficiency: Minimizing redundancy and optimizing queries

- Scalability: Allowing for growth like a thriving ecosystem

- Integrity: Ensuring data consistency and reliability

- Flexibility: Adapting to changing requirements like a resilient forest



We use PostgreSQL as our primary database management system, chosen for its robustness and eco-friendly efficiency.



## 📊 Main Tables



Our database consists of the following core tables:



1. **Users**: Stores user account information

2. **Products**: Contains details about our eco-friendly products

3. **Orders**: Tracks customer orders

4. **OrderItems**: Links products to orders

5. **Categories**: Organizes products into categories

6. **SustainabilityScores**: Stores sustainability metrics for products

7. **Reviews**: Contains user reviews for products

8. **Inventory**: Tracks product stock levels



## 🔗 Entity-Relationship Diagram (ERD)



Here's a simplified ERD of our main tables:



```

[Users] 1──N [Orders] 1──N [OrderItems] N──1 [Products]

                        |

                        |

                     1   |

                     |   |

                     N   1

                  [Reviews]  |

                        1

                        |

                        N

                    [Categories]

                        |

                        1

                        |

                        1

                [SustainabilityScores]

```



## 🌿 Detailed Schema



Here's a detailed look at each table's schema:



### Users Table



```sql

CREATE TABLE users (

  id SERIAL PRIMARY KEY,

  email VARCHAR(255) UNIQUE NOT NULL,

  password_hash VARCHAR(255) NOT NULL,

  first_name VARCHAR(100),

  last_name VARCHAR(100),

  created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP,

  updated_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP

);

```



### Products Table



```sql

CREATE TABLE products (

  id SERIAL PRIMARY KEY,

  name VARCHAR(255) NOT NULL,

  description TEXT,

  price DECIMAL(10, 2) NOT NULL,

  category_id INTEGER REFERENCES categories(id),

  created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP,

  updated_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP

);

```



### Orders Table



```sql

CREATE TABLE orders (

  id SERIAL PRIMARY KEY,

  user_id INTEGER REFERENCES users(id),

  status VARCHAR(50) NOT NULL,

  total_amount DECIMAL(10, 2) NOT NULL,

  created_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP,

  updated_at TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP

);

```



### OrderItems Table



```sql

CREATE TABLE order_items (

  id SERIAL PRIMARY KEY,

  order_id INTEGER REFERENCES orders(id),

  product_id INTEGER REFERENCES products(id),

  quantity INTEGER NOT NULL,

  price DECIMAL(10, 2) NOT NULL

);

```



### Categories Table



```sql

CREATE TABLE categories (

  id SERIAL PRIMARY KEY,

  name VARCHAR(100) NOT NULL,

  parent_id INTEGER REFERENCES categories(id)

);

```



### SustainabilityScores Table



```sql

CREATE TABLE sustainability_scores (

  id SERIAL PRIMARY KEY,

  product_id INTEGER UNIQUE REFERENCES products(id),

  overall_score INTEGER NOT NULL,

  carbon_footprint DECIMAL(10, 2),

  water_usage DECIMAL(10, 2),

  recyclability_score INTEGER

);

```



## 🔍 Indexing Strategy



We implement thoughtful indexing to optimize query performance:



```sql

-- Example indexes

CREATE INDEX idx_products_category ON products(category_id);

CREATE INDEX idx_orders_user ON orders(user_id);

CREATE INDEX idx_order_items_order ON order_items(order_id);

CREATE INDEX idx_order_items_product ON order_items(product_id);

```



## 🌱 Data Normalization



We follow Third Normal Form (3NF) to minimize data redundancy while balancing performance needs. For example, we separate product details from their sustainability scores.



## 🔗 Handling Relationships



We use foreign key constraints to maintain referential integrity:



```sql

ALTER TABLE products

ADD CONSTRAINT fk_product_category

FOREIGN KEY (category_id) REFERENCES categories(id);



ALTER TABLE order_items

ADD CONSTRAINT fk_order_item_order

FOREIGN KEY (order_id) REFERENCES orders(id);

```



## 🛡️ Data Integrity and Consistency



We ensure data integrity through:

- Use of transactions for critical operations

- Constraints (NOT NULL, UNIQUE, CHECK)

- Triggers for maintaining derived data



Example trigger:



```sql

CREATE OR REPLACE FUNCTION update_product_updated_at()

RETURNS TRIGGER AS $$

BEGIN

  NEW.updated_at = CURRENT_TIMESTAMP;

  RETURN NEW;

END;

$$ LANGUAGE plpgsql;



CREATE TRIGGER product_updated_at_trigger

BEFORE UPDATE ON products

FOR EACH ROW

EXECUTE FUNCTION update_product_updated_at();

```



## 🔄 Database Migrations



We use Django's migration system to version control our database schema:



```python

# Example migration

from django.db import migrations, models



class Migration(migrations.Migration):

  dependencies = [

    ('products', '0001_initial'),

  ]



  operations = [

    migrations.AddField(

      model_name='product',

      name='eco_friendly',

      field=models.BooleanField(default=True),

    ),

  ]

```



## 🚀 Performance and Scalability



To ensure our database can grow with our platform:

- We use appropriate data types to minimize storage requirements

- Implement partitioning for large tables (e.g., orders by date)

- Regularly analyze and optimize query performance

- Consider read replicas for scaling read operations



Example of table partitioning:



```sql

CREATE TABLE orders_partition (

  id SERIAL,

  user_id INTEGER,

  status VARCHAR(50),

  total_amount DECIMAL(10, 2),

  created_at TIMESTAMP WITH TIME ZONE

) PARTITION BY RANGE (created_at);



CREATE TABLE orders_2023_q1 PARTITION OF orders_partition

  FOR VALUES FROM ('2023-01-01') TO ('2023-04-01');



CREATE TABLE orders_2023_q2 PARTITION OF orders_partition

  FOR VALUES FROM ('2023-04-01') TO ('2023-07-01');

```



## 🌿 Continuous Improvement



Our database schema, like a thriving ecosystem, is always evolving:

- Regular reviews to identify optimization opportunities

- Performance monitoring and tuning

- Adapting to new business requirements while maintaining data integrity



By cultivating a well-structured, efficient database schema, we ensure that Ecolaura's data foundation is as sustainable and resilient as the natural world we're working to protect. Together, we're growing a data ecosystem that supports our mission of eco-friendly e-commerce! 🌿🗃️🌍