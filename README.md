### SeedFu
---
https://github.com/mbleigh/seed-fu

```
rake db:seed_fu

```

```ruby
# db/fixtures/users.rb
User.seed do |s|
  s.id = 1
  s.login = "jon"
  s.email = "jon@example.com"
  s.name = "Jon"
end
User.seed do |s|
  s.id = 2
  s.login = "emily"
  s.email = "emily@example.com"
  s.name = "Emily"
end

Point.seed(:x, :y) do |s|
  s.x = 4
  s.y = 7
  s.name = "Home"
end

Point.seed(:x, :y) do |s|
  s.x = 4
  s.y = 7
  s.name = "Work"
end

Point.seed_once(:x, :y) do |s|
  s.x = 4
  s.y = 7
  s.name = "Home"
end

User.seed(:id,
  { :id => 1, :login => "jon", :email => "jon@ex.com", :name => "Jon" },
  { :id => 2, :login => "emily", :email => "emily@ex.com", :name => "Emily" }
)

require 'seed-fu/capistrano'
after 'deploy:update_code', 'db:seed_fu'
require 'seed-fu/capistrano3'
before 'deploy:publishing', db:seed_fu'



```

```

```
