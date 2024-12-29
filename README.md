<p align="center">
    <b style="font-size: 30px;">Anti Gcast API</b>
    <br>
    <a href="https://antigcast.vercel.app/">
        Homepage
    </a>
    •
    <a href="https://github.com/AyiinXd/AntiGcast/releases">
        Releases
    </a>
    •
    <a href="https://t.me/AyiinChats">
        News
    </a>
</p>

### Anti Gcast API

> Anti Gcast API For Clean Incoming Message On Telegram Groups.

## Python Example
``` python
from requests import post

async def antiGcast(text):
    response = post(
        "https://antigcast.vercel.app/",
        json={
            "text": text
        },
        headers={
            "Content-Type": "application/json"
        }
    )
    return response.json()

print(antiGcast("test"))
```

## Node Example
``` javascript
import axios from "axios";
// or
const axios = require("axios");

async function antiGcast(text) {
    const response = await axios.post(
        "https://antigcast.vercel.app/",
        {
            text
        },
        {
            headers: {
                "Content-Type": "application/json"
            }
        }
    );
    return response.data;
}
console.log(antiGcast("test"));
```

## Go Example
``` go
package main

import (
    "fmt"
    "net/http"
    "encoding/json"
)

func main() {
    client := &http.Client{}
    data := map[string]string{
        "text": "test",
    }
    jsonData, _ := json.Marshal(data)
    req, _ := http.NewRequest("POST", "https://antigcast.vercel.app/", bytes.NewBuffer(jsonData))
    req.Header.Set("Content-Type", "application/json")
    resp, _ := client.Do(req)
    var result map[string]interface{}
    json.NewDecoder(resp.Body).Decode(&result)
    fmt.Println(result)
}
```

## C# Example
``` c#
using System;
using System.Net.Http;
using System.Net.Http.Json;
using System.Text.Json;

var client = new HttpClient();
var data = new
{
    text = "test"
};
var jsonData = JsonSerializer.Serialize(data);
var content = new StringContent(jsonData, null, "application/json");
var response = await client.PostAsync("https://antigcast.vercel.app/", content);
var result = await response.Content.ReadFromJsonAsync<Dictionary<string, object>>();
Console.WriteLine(result);
```

## Java Example
``` java
import java.net.http.HttpClient;
import java.net.http.HttpRequest;
import java.net.http.HttpResponse;
import java.net.http.HttpRequest.BodyPublishers;
import java.net.http.HttpResponse.BodyHandlers;
import java.util.Map;

var client = HttpClient.newHttpClient();
var data = Map.of("text", "test");
var request = HttpRequest.newBuilder()
    .uri(URI.create("https://antigcast.vercel.app/"))
    .POST(BodyPublishers.ofString(Json.stringify(data)))
    .build();
var response = client.send(request, BodyHandlers.ofString());
var result = Json.decodeValue(response.body(), Map.class);
System.out.println(result);
```

## Ruby Example
``` ruby
require "uri"
require "net/http"
require "json"

def antiGcast(text)
  uri = URI("https://antigcast.vercel.app/")
  http = Net::HTTP.new(uri.host, uri.port)
  http.use_ssl = true
  request = Net::HTTP::Post.new(uri)
  request["Content-Type"] = "application/json"
  request.body = { text: text }.to_json
  response = http.request(request)
  JSON.parse(response.body)
end

puts antiGcast("test")
```

## Kotlin Example
``` kotlin
import java.net.http.HttpClient
import java.net.http.HttpRequest
import java.net.http.HttpResponse
import java.net.http.HttpRequest.BodyPublishers
import java.net.http.HttpResponse.BodyHandlers
import java.util.Map

fun main() {
    val client = HttpClient.newHttpClient()
    val data = mapOf("text" to "test")
    val request = HttpRequest.newBuilder()
        .uri(URI.create("https://antigcast.vercel.app/"))
        .POST(BodyPublishers.ofString(Json.stringify(data)))
        .build()
    val response = client.send(request, BodyHandlers.ofString())
    val result = Json.decodeValue(response.body(), Map::class.java)
    println(result)
}
```

## Dart Or Flutter Example
``` dart
import 'package:http/http.dart' as http;

Future<Map<String, dynamic>> antiGcast(String text) async {
  final response = await http.post(
    Uri.parse('https://antigcast.vercel.app/'),
    headers: {'Content-Type': 'application/json'},
    body: json.encode({'text': text}),
  );
  return json.decode(response.body) as Map<String, dynamic>;
}

void main() async {
  final result = await antiGcast('test');
  print(result);
}
```

## Swift Example
``` swift
import Foundation
import Alamofire

func antiGcast(text: String) async throws -> [String: Any] {
    let url = URL(string: "https://antigcast.vercel.app/")!
    let parameters: [String: Any] = ["text": text]
    let headers: HTTPHeaders = ["Content-Type": "application/json"]
    let response = try await AF.request(url, method: .post, parameters: parameters, headers: headers).responseJSON()
    return response.result.value as? [String: Any] ?? [:]
}

let result = try await antiGcast(text: "test")
print(result)
```

## PHP Example
``` php
<?php
$data = json_encode(array("text" => "test"));
$ch = curl_init("https://antigcast.vercel.app/");
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "POST");
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, array(
    "Content-Type: application/json"
);
$result = curl_exec($ch);
curl_close($ch);
echo $result;
```


## Support and Contact
  - For further questions or technical support, please contact the development team on group [t.me/AyiinChats](https://t.me/AyiinChats).

  - Join our community forum to share experiences and get help from other developers.