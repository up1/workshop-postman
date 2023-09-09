## Workshop with [Thailand Post API](https://track.thailandpost.co.th/developerGuide)
* Change pattern of regular expression of date
  * DD/MM/YYYY
  * [match function](https://www.chaijs.com/api/bdd/#method_match)


Test case
```
pm.test("Format track_date", function () {
    let jsonData = pm.response.json();
    pm.expect(jsonData.response.track_count.track_date).to.match(/^(0?[1-9]|[12][0-9]|3[01])\/(0?[1-9]|1[0-2])\/\d{4}$/);
});
```

Run with Global variable
```
$newman run thailand_post_tracking.postman_collection.json --global-var  "USER_TOKEN=YOUR_TOKEN"
```