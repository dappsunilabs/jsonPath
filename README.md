# jsonPath

## Script to query JSON data

### Example
```
<script type="text/javascript">
         	  var json = { "MovieDatabase": {
  "movie": [ 
         	  { "name":"The Change-Up",
  "genre": "comedy",
  "director": "David Dobkin",
  "Facebook_like": 252
         	  },
         	  { "name":"Rise of the Planet of the Apes",
  "genre": "SciFi",
  "director": "Rupert Wyatt",
  "Facebook_like": 472
         	  },
         	  { "name":"30 Minutes or Less",
  "genre": "adventure",
  "director": "Ruben Fleischer",
  "Facebook_like": 114
         	  },
         	  { "name":"Final Destination 5",
  "genre": "Horror",
  "director": "Steven Quale",
  "Facebook_like": 241
         	  }
         	  ]
         	  }
         	  };
         	  result = "";
         	  result += jsonPath(json, "$.MovieDatabase.movie[*].director").toJSONString() + "<br />";
         	  //find all directors
         	  result += jsonPath(json, "$..director").toJSONString() + "<br />";
         	  //find all directors
         	  result += jsonPath(json, "$.MovieDatabase.*").toJSONString() + "<br />";
         	  //find all movies
         	  result += jsonPath(json, "$.MovieDatabase..Facebook_like").toJSONString() + "<br />";
         	  //find all facebook lies of all the movies
         	  result += jsonPath(json, "$..movie[(@.length-1)]").toJSONString() + "<br />";
         	  //the last movie in data
         	  result += jsonPath(json, "$..movie[-1:]").toJSONString() + "<br />";
         	  //the last movie in data
         	  result += jsonPath(json, "$..movie[0,1]").toJSONString() + "<br />";
         	  //first two movies
         	  result += jsonPath(json, "$..movie[:3]").toJSONString() + "<br />";
         	  //first three movies
         	  result += jsonPath(json, "$..movie[?(@.genre)]").toJSONString() + "<br />";
         	  //all movies with genre
         	  result += jsonPath(json, "$..movie[?(@.Facebook_like>200)]").toJSONString() + "<br />";
         	  //movies with facebook like more that 200
         	  result += jsonPath(json, "$..*").toJSONString() + "\n";
         	  // all members in the JSON document
         	  document.write(result);
  </script>
  ```
