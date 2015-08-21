---
permalink: "/cheatsheets/rails/active-model-serializers/"
layout: page
title:  "Rails: Active Model Serializers"
---

<ol class="breadcrumb">
  <li><a href="/cheatsheets">Cheatsheets</a></li>
  <li><a href="/cheatsheets/rails">Rails</a></li>
  <li class="active">Active Model Serializers</li>
</ol>

## Configuring Format for Keys

### For the whole project

config/initializers/active_model_serializer.rb

```ruby
ActiveModel::Serializer.setup do |config|
  config.key_format = :lower_camel
end
```

### For an individual serializer or a base serializer

Currently, only `lower_camel` is supported.  If we want none just put `format_keys :none`

```ruby
class BlogLowerCamelSerializer < ActiveModel::Serializer
  format_keys :lower_camel
end
```

https://github.com/rails-api/active_model_serializers/pull/534

### Possibly a new addition

https://github.com/rails-api/active_model_serializers/pull/1029

## Formats

In the works are multiple types of JSON formats.  However, some libraries (like https://github.com/google/google-api-ruby-client) abstract out their interface for hashes.  So, to convert to a hash, we can just parse the json.

```ruby
JSON.parse(MyModelSerializer.new(my_model).to_json)
```

Or we can add a base class
```ruby
class BaseSerializer < ActiveModel::Serializer
    def hashed
      JSON.parse(self.to_json)
    end
end

# Then call it like
MyModelSerializer.new(my_model).hashed
```