# Hub Wiremock Content Feed

This is a small project using [Wiremock](http://wiremock.org/) to simulate the REST api and provide canned responses to test the Laravel front-end of the Hub.

The project is automatically deployed to Heroku and started using a Procfile with the following command:

```
web: java $JAVA_OPTS -Dserver.port=$PORT -jar wiremock-standalone-2.6.0.jar --port $PORT
```

## Testing Locally

Wiremock can be tested locally by using the following command and viewed here http://localhost:8080/api/hub/

```
java -jar wiremock-standalone-2.6.0.jar
```

Or using Heroku, note that when testing with Heroku to make a note of the port number provided within terminal.

```
heroku local web
```

## Mappings & Expected responses

Mappings have been provided for the following end points.

### Hub Front Page

* https://hub-content-feed-mock.herokuapp.com/api/hub/

```
{
  "id":null,
  "title":"Digital Hub",
  "icon":null,
  "links":[
    {
      "nid":"116",
      "title":"Education",
      "thumbnail":"app_education.png",
      "url":null,
      "parent":null
    },
    {
      "nid":"118",
      "title":"Video",
      "thumbnail":"app_video.png",
      "url":"\/video",
      "parent":null
    },
    {
      "nid":"119",
      "title":"Radio",
      "thumbnail":"app_audio.png",
      "url":"\/radio",
      "parent":null
    },
    {
      "nid":"1831",
      "title":"Books",
      "thumbnail":"app_books.png",
      "url":null,
      "parent":null
    }
  ]
}
```

### Education

* https://hub-content-feed-mock.herokuapp.com/api/hub/116

```
{
  "id":"116",
  "title":"Education",
  "icon":"http:\/\/moj-hub-dev001.northeurope.cloudapp.azure.com:81\/sites\/default\/files\/2016-10\/app_education.png",
  "parent":{
    "id":null,
    "title":"Digital Hub"
  },
  "links":[
    {
      "nid":"120",
      "title":"NEC Courses",
      "thumbnail":"http://moj-hub-dev001.northeurope.cloudapp.azure.com:81\/sites\/default\/files\/2016-10\/NEC%20Temp.png",
      "url":"\/education\/7",
      "parent":[
        {
          "target_id":"116"
        }
      ]
    },
    {
      "nid":"2501",
      "title":"Way2Learn",
      "thumbnail":"http://moj-hub-dev001.northeurope.cloudapp.azure.com:81\/sites\/default\/files\/2016-12\/Way2LearnHubTile.png",
      "url":"\/video\/channel\/191",
      "parent":[
        {
          "target_id":"116"
        }
      ]
    },
    {
      "nid":"1051",
      "title":"Shannon Trust",
      "thumbnail":"http://moj-hub-dev001.northeurope.cloudapp.azure.com:81\/sites\/default\/files\/2016-11\/Shannon%20Trust%20Placeholder.png",
      "url":"\/education\/451",
      "parent":[
        {
          "target_id":"116"
        }
      ]
    }
  ]
}
```

### NEC Courses

* https://hub-content-feed-mock.herokuapp.com/api/pdf/course/7

```
{
  "parent":{
  "cat_id":"7",
  "cat_name":"National Extension College",
  "cat_description":"\u003Cp\u003EIf you study on a course with the NEC, you will receive a pack of course materials and a tutor who will provide you with all of the resources you need to complete the qualification. In the sample course material below you may find links to content that you cannot access from within your prison. Don\u0027t worry about this as you will be able to find all of this information in your resource pack.\u003C\/p\u003E\r\n\r\n\u003Cp\u003E\u0026nbsp;\u003C\/p\u003E\r\n",
  "additional_description":null,
  "cat_banner":"",
  "back_link":"/hub/116"
  },
  "children":[
    {
      "tid":"371",
      "name":"Distance Learning",
      "parent":null,
      "cat_description":null,
      "additional_description":null
    },
    {
      "tid":"8",
      "name":"Art \u0026 Literature",
      "parent":null,
      "cat_description":null,
      "additional_description":null
    },
    {
      "tid":"9",
      "name":"Business \u0026 Economics",
      "parent":null,
      "cat_description":null,
      "additional_description":null
    },
    {
      "tid":"10",
      "name":"Counselling \u0026 Psychology",
      "parent":null,
      "cat_description":null,
      "additional_description":null
    },
    {
      "tid":"11",
      "name":"English",
      "parent":null,
      "cat_description":null,
      "additional_description":null
    },
    {
      "tid":"12",
      "name":"Environmental Studies",
      "parent":null,
      "cat_description":null,
      "additional_description":null
    },
    {
      "tid":"13",
      "name":"Foreign Languages",
      "parent":null,
      "cat_description":null,
      "additional_description":null
    },
    {
      "tid":"14",
      "name":"History",
      "parent":null,
      "cat_description":null,
      "additional_description":null
    },
    {
      "tid":"15",
      "name":"Law \u0026 Politics",
      "parent":null,
      "cat_description":null,
      "additional_description":null
    },
    {
      "tid":"16",
      "name":"Maths",
      "parent":null,
      "cat_description":null,
      "additional_description":null
    },
    {
      "tid":"17",
      "name":"Philosophy",
      "parent":null,
      "cat_description":null,
      "additional_description":null
    },
    {
      "tid":"18",
      "name":"Science",
      "parent":null,
      "cat_description":null,
      "additional_description":null
    },
    {
      "tid":"19",
      "name":"Sociology",
      "parent":null,
      "cat_description":null,
      "additional_description":null
    }
  ]
}
```
