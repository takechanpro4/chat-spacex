##usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|index: true, null:false, |  |nique: true|
|mail|string|null: false|
|passrord|string|null: false|

###Association
- has_many :groups, through: members :through: :members
- has_many :messages
- has_many :members,

##groupsテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null: false, unique: true

###Association
- has_many :users, through: :members
- has_many :messages
- has_many :menbers 


##messagesテーブル

|Column|Type|Options|
|------|----|-------|
|body|string|
|image|string|
|users_id|reference|null: false, - - - foreign_key: true 
|groups_id|reference|null: false, foreign_key: true

###Association
- belongs_to :group
- belongs_to :user


##membersテーブル

|Column|Type|Options|
|------|----|-------|
|users_id|reference|null:false, |foreign_key: true|
|groups_id|reference|null: false, foreign_key: true|

###Association
- belongs_to :group
- belongs_to :user
