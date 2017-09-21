## A simple guide to learn Handlebar


##### JavaScript

```javascript

 $(function () {
            var addressTextScript = $("#hb_Address").html();
            var addressText = Handlebars.compile(addressTextScript);

            var addressDetails = {
                "companyName": "Opensource-It",
                "city": "Dhaka",
                "phone": "+88 1715836598",
                "php" : "<p><?php echo 'Hello World'; ?></p>",
                "email": "<a class='btn btn-info btn-sm' href='mailto:mominriyadh@gmail.com'>Email Us</a><br>",
                peoples: [
                    {
                        "firstName": "Momin",
                        "lastName": "Riyadh"
                    },
                    {
                        "firstName": "Zakaria",
                        "lastName": "Shopon"
                    },
                    {
                        "firstName": "Abdul",
                        "lastName": "Mannan"
                    }
                ]

            };
            var compiledHtml = addressText(addressDetails);
            $('#address').html(compiledHtml);
        });
```


#### Handlebar Template
```javascript
<script id="hb_Address" type="text/x-handlebars-template">
    <address>
        {{companyName}} <br/>
        City: {{city}} <br/>
        Phone: {{phone}} <br/>
        PHP: {{{php}}} <br/>
        {{{email}}}

        <ul class="list-group">
            {{#each peoples}}
                <li class="list-group-item">{{firstName}} {{lastName}}</li>
            {{/each}}
        </ul>
    </address>


</script>

```

#### HTML Markup
```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Learn Handlebars</title>
    <link rel="stylesheet" href="node_modules/bootstrap/dist/css/bootstrap.css">

    <script src="node_modules/jquery/dist/jquery.js"></script>
    <script src="node_modules/handlebars/dist/handlebars.js"></script>
    <script>
        $(function () {
            var addressTextScript = $("#hb_Address").html();
            var addressText = Handlebars.compile(addressTextScript);

            var addressDetails = {
                "companyName": "Opensource-It",
                "city": "Dhaka",
                "phone": "+88 1715836598",
                "php" : "<p><?php echo 'Hello World'; ?></p>",
                "email": "<a class='btn btn-info btn-sm' href='mailto:mominriyadh@gmail.com'>Email Us</a><br>",
                peoples: [
                    {
                        "firstName": "Momin",
                        "lastName": "Riyadh"
                    },
                    {
                        "firstName": "Zakaria",
                        "lastName": "Shopon"
                    },
                    {
                        "firstName": "Abdul",
                        "lastName": "Mannan"
                    }
                ]

            };
            var compiledHtml = addressText(addressDetails);
            $('#address').html(compiledHtml);
        });


    </script>
</head>
<body>
<script id="hb_Address" type="text/x-handlebars-template">
    <address>
        {{companyName}} <br/>
        City: {{city}} <br/>
        Phone: {{phone}} <br/>
        PHP: {{{php}}} <br/>
        {{{email}}}

        <ul class="list-group">
            {{#each peoples}}
                <li class="list-group-item">{{firstName}} {{lastName}}</li>
            {{/each}}
        </ul>
    </address>


</script>
<br/>
<br/>
<div class="container">
    <div class="row">
        <div class="col-sm-6 col-sm-offset-3">
            <div class="jumbotron">
                <div id="address"></div>
            </div>
        </div>
    </div>
</div>

</body>
</html>
```

Thats it !