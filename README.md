# Immigration Network

#### Step-1: FB Data

to load into mongodb run the following commands:

```
mongoimport --db <dbname> --collection <collectionName> --drop --file <filename>.json
mongoimport --db unicief --collection syrpages --drop --file /Users/Suad/FB-data/pages_15_12_2015.json
mongoimport --db unicief --collection syrposts --drop --file /Users/Suad/FB-data/posts_15_12_2015.json
mongoimport --db unicief --collection syrcomments --drop --file /Users/Suad/FB-data/comments_15_12_2015.json
mongoimport --db unicief --collection syrlikes --drop --file /Users/Suad/FB-data/likes_15_12_2015.json
```

#### Step-2: Pages Filter 

1. Filter based on specific categories
2. Remove specific keywords 
3. Remove pages with no likes

#### Step-3: Users - Posts Network
1. From the resulted relevant pages we can get relevant posts (Post record contains page_id)
2. From the resulted relevant posts we cant get relevant comments (Comment record contains post_id in field id (post_id+comment_id), then we can get relevant users from the field _from_ {id, user}) 

3. As step 2. we can get relevant likes (Like record id: post_id+like_id) but it offers only _name_ of user
