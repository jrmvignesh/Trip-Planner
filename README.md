# cmpe273-tripplanner

CURL commands

POST REQUEST 

curl  -H "Content-Type: application/json" -X POST -d '{"StartPt" : "5643fd4c791dee13c8d3c669", "Location_ids" : ["5643fd59791dee13c8d3c66a" , "5643fd63791dee13c8d3c66b" , "5643fd6d791dee13c8d3c66c" ]}' http://127.0.0.1:8080/trips

Response  :
{"id":"12351","status":"Planning","starting_from_location_id":"5643fd4c791dee13c8d3c669","Bestlocation_ids":["5643fd63791dee13c8d3c66b","5643fd59791dee13c8d3c66a","5643fd6d791dee13c8d3c66c"],"total_uber_costs":81,"total_uber_duration":3742,"Distance":38.870000000000005}

GET REQUEST : 

curl -X GET http://127.0.0.1:8080/trips/12351

Response : 
{"id":"12351","status":"Planning","starting_from_location_id":"5643fd4c791dee13c8d3c669","Bestlocation_ids":["5643fd63791dee13c8d3c66b","5643fd59791dee13c8d3c66a","5643fd6d791dee13c8d3c66c"],"total_uber_costs":81,"total_uber_duration":3742,"Distance":38.870000000000005}

PUT request

curl -H "Content-Type: application/json" -X PUT -d '{"status":"requesting"}' -H 'Authorization:Bearer <access token not disclosed>' http://127.0.0.1:8080/trips/12351

Response : 

{
    "_id": "12351",
    "status": "requesting",
    "starting_from_location_id": "5643fd4c791dee13c8d3c669",
    "next_destination_location_id": "5643fd63791dee13c8d3c66b",
    "Bestlocation_ids": [
        "5643fd63791dee13c8d3c66b",
        "5643fd59791dee13c8d3c66a",
        "5643fd6d791dee13c8d3c66c"
    ],
    "total_uber_costs": 81,
    "total_uber_duration": 3742,
    "distance": 38.870000000000005,
    "eta": 187
}
