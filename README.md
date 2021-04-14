# sql2es
Use sql grammar change ES dsl

1. select * from test;

2. select * from test where a = 1;

3. select * from test where a = 1 && b = 2;

4. select * from test where a = 1 && b like "Google";

5. select * from test where (a = 1 || b = 2) && c = 3;

6. select * from test where (a = 1 || b = 2) && c in (1,2,3);

7. select a,b,c from test where (a = 1 || b = 2) && c in (1,2,3);

8. select a,b,c from test where (a = 1 || b = 2) && c like_in ("百度","Google","Bing");

9. select a,b,c from test limit 1,10;

10. select * from test order by id desc,id2 asc;

```


```
var sql2es = require('sql2es');

sql2es('select * from test;', function(err, q) {
  console.log(err, q);
});
```

key  |  value
------------ | -------------
= | term
&& | must
|| | should
!= | must_not
like | query_string
like_in | query_string
and | must
or | should
in | terms
