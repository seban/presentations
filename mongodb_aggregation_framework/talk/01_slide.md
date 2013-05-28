!SLIDE
# mongoDb Aggregation Framework  #
## Sebastian Nowak

!SLIDE bullets incremental
# mongoDb  #

* group
* mapReduce

!SLIDE center transition=scrollLeft
![Fireworks](fireworks.jpg)

!SLIDE incremental transition=scrollDown
# mongodb 2.2

## +++ Aggregation framework

!SLIDE commandline transition=fade

    $ grep "my word" | sort | uniq -c | head -n100

!SLIDE small

    @@@ javascript
    db.offers.aggregate([
      {"$match": {"category_id": 9990}},
      {"$group": {
        "_id": {"category_id": "$category_id",
                "is_matched": "$is_matched"},
        "offers_count": {"$sum": 1}}}
    ])

!SLIDE smaller

    @@@javascript
    db.offers.aggregate([
      {"$match": {"category_id": 9990}},
      {"$group": {
        "_id": { "pattern_id": "$matched_pattern_id"},
        "offers_count": { "$sum": 1 },
        "avg_price": {"$avg": "$price"}
      }},
      {"$project": {"pattern_id": "$_id.pattern_id",
                    "offers_count": 1,
                    "avg_price": 1, "_id": 0}},
      {"$sort": {"offers_count": -1, "avg_price": -1}},
      {"$limit": 10}
    ])

!SLIDE small

    @@@javascript
    db.offers.aggregate([
       {"$match": {"category_id": 9990}},
       {"$group": {
         "_id": {"pattern_id": "$matched_pattern_id"},
         "titles": {"$addToSet": "$title"}
       }}
       {"$limit": 10}
    ])

!SLIDE smaller

    @@@javascript
    db.offers.aggregate([
      {"$match": {
        "category_id": 9990,
        "offer_properties.title": "waga"}},
      {"$project": {
        "offer_properties.title": 1,
        "offer_properties.value": 1}},
      {"$unwind": "$offer_properties"},
      {"$match": {"offer_properties.title": "waga"}},
      {"$group": {
        "_id": "$offer_properties.title",
        "values": {"$addToSet":
          {"$ifNull": ["$offer_properties.value", ""]}}}}
    ])

!SLIDE small

    @@@javascript
    db.clicks.aggregate([
      {"$group": {
        "_id": {
           "dow": {"$dayOfWeek": "$created_at"},
           "hod": {"$hour": "$created_at"}
        },
        "count": {"$sum": 1},
        "avg_value": {"$avg": "$value"},
        "min_value": {"$min": "$value"},
        "max_value": {"$max": "$value"}
      }}
    ])

!SLIDE center

# $geoNear

!SLIDE center

# Sharded

![Checked](check.svg.png)

!SLIDE incremental center

## 5%

# 10%

!SLIDE center

# ?
