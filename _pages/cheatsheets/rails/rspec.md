---
permalink: "/cheatsheets/rails/rspec/"
layout: page
title:  "Rails: RSpec"
---

## Tips

### Puts from Rspec
```ruby
$stderr.puts "method TEXT"
```


## Examples

### Raise Exception

```ruby
  context 'invalid card number' do
    let(:credit_account) { FactoryGirl.create(:credit_account, number: '1234') }

    it 'should validate the number against luhn correctly' do
      expect { credit_account.is_valid? }.to raise_error(ActiveRecord::RecordInvalid,
        'Validation failed: Number is not valid')
    end
  end

  context 'valid card number' do
    let(:credit_account) { FactoryGirl.create(:credit_account, number: '4242424242424242') }

    it 'should catch pass validation for valid luhn numbers' do
      expect { credit_account.is_valid? }.not_to raise_error
    end

    it 'should default balance to 0' do
      expect(credit_account.balance).to eq 0
    end
  end
  ```


