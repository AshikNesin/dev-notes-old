become active record migration expert (Rails 4.0.2)
============================================

workflow:

### create model
``` shell
$ rails g model NameOfModel
    invoke  active_record
    create    db/migrate/YYYYMMDDHHMMSS_create_name_of_models.rb
    create    app/models/name_of_model.rb
    invoke    test_unit
    create      test/models/name_of_model_test.rb
    create      test/fixtures/name_of_models.yml

```

### create `name_of_models` table and define some columns

1. open `db/migrate/YYYYMMDDHHMMSS_create_name_of_models.rb`

2. define field in format `t.field_type :field_name`
``` ruby
class CreateNameOfModels < ActiveRecord::Migration
    def change
        create_table :name_of_models do |t|
            t.string :name
            t.integer :age
            t.timestamps
        end
    end
end
```

3. run `rake db:migrate`
``` shell
$ rake db:migrate
==  CreateNameOfModels: migrating =============================================
-- create_table(:name_of_models)
   -> 0.0085s
==  CreateNameOfModels: migrated (0.0087s) ====================================
```
this will create `name_of_models` table with `name` and `age` columns.

### updating `name_of_models` table

#### add another column
1. run rails generator with `Add[column]To[model]` format followed by column
``` shell
$ rails g migration AddBioToNameOfModels bio:text
    invoke  active_record
    create    db/migrate/YYYYMMDDHHMMSS_add_bio_to_name_of_models.rb
```

2. open `db/migrate/YYYYMMDDHHMMSS_add_bio_to_name_of_columns.rb`
``` ruby
class AddBioToNameOfModels < ActiveRecord::Migration
  def change
    add_column :name_of_models, :bio, :text
  end
end
```

3. run `rake db:migrate`
``` shell
› rake db:migrate
==  AddBioToNameOfModels: migrating ===========================================
-- add_column(:name_of_models, :bio, :text)
   -> 0.0067s
==  AddBioToNameOfModels: migrated (0.0069s) ==================================
```

#### add multiple columns at once

1. run rails generator with `AddDetailsTo[model]` format followed by list of columns
``` shell
$ rails g migration AddDetailsToNameOfModels first_name last_name phone_number anothertables:belongs_to
    invoke  active_record
    create    db/migrate/YYYYMMDDHHMMSS_add_details_to_name_of_models.rb
```

2. open up `db/migrate/YYYYMMDDHHMMSS_add_details_to_name_of_models.rb`
``` ruby
class AddDetailsToNameOfModels < ActiveRecord::Migration
    def change
        add_column :name_of_models, :first_name, :string
        add_column :name_of_models, :last_name, :string
        add_column :name_of_models, :phone_number, :string
        add_reference :name_of_models, :anothertables, index: true
    end
end
```
make sure you have exactly column name and type before migrating

3. run `rake db:migrate`
``` shell
$ rake db:migrate
==  AddDetailsToNameOfModels: migrating =======================================
-- add_column(:name_of_models, :first_name, :string)
   -> 0.0068s
-- add_column(:name_of_models, :last_name, :string)
   -> 0.0009s
-- add_column(:name_of_models, :phone_number, :string)
   -> 0.0008s
-- add_reference(:name_of_models, :anothertables, {:index=>true})
   -> 0.0016s
==  AddDetailsToNameOfModels: migrated (0.0108s) ==============================
```

#### remove column

1. run rails generator with `Remove[column]From[model]` format followed by column you want to remove
``` shell
$ rails g migration RemovePhoneNumberFromNameOfModels phone_number:string
      invoke  active_record
      create    db/migrate/YYYYMMDDHHMMSS_remove_phone_number_from_name_of_models.rb
```

2. open `db/migrate/YYYYMMDDHHMMSS_remove_phone_number_from_name_of_models` to make sure.
``` ruby
class RemovePhoneNumberFromNameOfModels < ActiveRecord::Migration
    def change
        remove_column :name_of_models, :phone_number, :string
    end
end
```

#### remove multiple columns at once
1.  run rails generator with `RemoveDetailsFrom[model]` format followed by column you want to remove
``` shell
› rails g migration RemoveDetailsFromNameOfModels first_name last_name anothertables:belongs_to
      invoke  active_record
      create    db/migrate/YYYYMMDDHHMMSS_remove_details_from_name_of_models.rb
```

2. open `db/migrate/YYYYMMDDHHMMSS_remove_details_from_name_of_models.rb`
``` ruby
class RemoveDetailsFromNameOfModels < ActiveRecord::Migration
    def change
        remove_column :name_of_models, :first_name, :string
        remove_column :name_of_models, :last_name, :string
        remove_reference :name_of_models, :anothertables, index: true
    end
end
```
3. if you are sure with what you do, then run `rake db:migrate`. it will remove all column or reference that you define on `db/migrate/YYYYMMDDHHMMSS_remove_details_from_name_of_models.rb`

### tips
 - when you migrate the wrong table you can rollback using `rake db:rollback`
 - update your table with create new migration (add/remove). 

> I think, updating your table by editing your previous migration is not best practice. my experience updating table by editing my previous migration and then execute `rake db:migrate` is doesn't work. 

## more resource
[Active Record Migrations][ar]

[ar]: http://guides.rubyonrails.org/migrations.html
