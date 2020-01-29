# Active Record

These are the **Models**.`

## Naming Tables

- Active Record pluralizes the name of the Model to create the database table name.
- If there are two words, PascalCase them.

| Model Name | Database table |
| ---------- | -------------- |
| Article    | articles       |
| LineItem   | line_items     |
| Deer       | deers          |
| Mouse      | mice           |
| Person     | people         |

## Naming Columns

- Foreign keys: `singularized_table_name_id`
- Primary keys: `id` is default.

`.timestamps` create `created-at`, `updated-at`.

There are other default columns, something to be vary of is the `type` column. This is used by Rails for tables with [Single Table Inheritance](https://api.rubyonrails.org/v6.0.2.1/classes/ActiveRecord/Inheritance.html).

## Creating a Model

```ruby
class Thing < ApplicationRecord
end
```

> You can override the rails column defaults.

## CRUD

1. Create

```ruby
# Create & Save
user = User.create(name: "David", occupation: "Coder")

# Create instance but not save
user = User.new
user.name = "David"
user.occupation = "Coder"
# This actually saves it
user.save
```

2. Read

```ruby
User.all
User.first
User.find_by(name: 'David')
```

3. Update

```ruby
user = User.find_by(name: 'David')
user.update(name: 'Dave')
```

4. Destroy

```ruby
user = User.find_by(name: "David")
user.destroy

# Destroy multiple records
User.destroy_by(name: "David")
# Destroy all records
User.destroy_all
```

## Validation

```ruby
class User < ApplicationRecord
  validates :name, presence: true
end
```
