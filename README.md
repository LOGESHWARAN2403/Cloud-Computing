
Sample Source Code

Here’s a basic example of how you can define the intents and slots in Amazon Lex:


{
  "intents": [
    {
      "name": "BookHotel",
      "slots": [
        {
          "name": "RoomType",
          "slotType": "RoomType",
          "slotTypeVersion": "1",
          "valueElicitationPrompt": {
            "messages": [
              {
                "contentType": "PlainText",
                "content": "What type of room would you like to book? (Classic, Duplex, etc.)"
              }
            ],
            "maxAttempts": 2
          },
          "priority": 1
        },
        {
          "name": "CheckInDate",
          "slotType": "AMAZON.DATE",
          "valueElicitationPrompt": {
            "messages": [
              {
                "contentType": "PlainText",
                "content": "What is your check-in date?"
              }
            ],
            "maxAttempts": 2
          },
          "priority": 2
        },
        {
          "name": "CheckOutDate",
          "slotType": "AMAZON.DATE",
          "valueElicitationPrompt": {
            "messages": [
              {
                "contentType": "PlainText",
                "content": "What is your check-out date?"
              }
            ],
            "maxAttempts": 2
          },
          "priority": 3
        },
        {
          "name": "NumberOfGuests",
          "slotType": "AMAZON.NUMBER",
          "valueElicitationPrompt": {
            "messages": [
              {
                "contentType": "PlainText",
                "content": "How many guests will be staying?"
              }
            ],
            "maxAttempts": 2
          },
          "priority": 4
        }
      ],
      "fulfillmentActivity": {
        "type": "ReturnIntent"
      }
    }
  ],
  "slotTypes": [
    {
      "name": "RoomType",
      "description": "Types of rooms available",
      "enumerationValues": [
      {
          "value": "Classic"
        },
        {
          "value": "Duplex"
        },
        {
          "value": "Suite"
        }
      ]
    }
  ]
}
