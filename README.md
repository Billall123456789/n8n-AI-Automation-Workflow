{
  "nodes": [
    {
      "parameters": {
        "httpMethod": "POST",
        "path": "https://snthreesixty.app.n8n.cloud/webhook-test/foodie-corner-webhook",
        "responseMode": "=onReceived",
        "options": {}
      },
      "id": "4a6965b5-1470-4765-a04b-7aa341a49c54",
      "name": "Webhook",
      "type": "n8n-nodes-base.webhook",
      "typeVersion": 1,
      "position": [
        -280,
        -120
      ],
      "webhookId": "foodie-corner-orders"
    },
    {
      "parameters": {
        "respondWith": "json",
        "responseBody": "={\n  \"success\": true,\n  \"message\": \"Order confirmed successfully!\",\n  \"customer_name\": \" Bilal\",\n  \"Sale_amount\": 0,\n  \"estimated_delievey_time\": \" N/A\",\n  \"order_type\": \"Delivery\",\n  \"delivery_address\": \" ABC Street G13, Islamabad\",\n  \"payment_method\": Cash on Delivery\"\",\n  \"food item\": \" 3 x Pasta, 2 x Chicken Steaks, 1 x Medium Coke\",\n  \"delievery status\":  N/A,\n  \"phone\": 12345678,\n\"delievery status\": N/A,\n  \"kitchen_notification\": \"Order sent to kitchen successfully\",\n  \"next_steps\": \"Your delicious meal is being prepared! You'll receive SMS updates about your order status.\",\n  \"restaurant_contact\": \"+92-XXX-XXXXXXX\",\n  \"thank_you_message\": \"Thank you for choosing Foodie Corner! We're excited to serve you.\"\n}",
        "options": {}
      },
      "id": "32abdb5b-24a4-4cfb-b4ee-c6bc9d88dc28",
      "name": "Respond to Webhook",
      "type": "n8n-nodes-base.respondToWebhook",
      "typeVersion": 1,
      "position": [
        380,
        -120
      ]
    },
    {
      "parameters": {
        "operation": "append",
        "documentId": {
          "__rl": true,
          "value": "1IRcNkemHx4SpUJ65uvrNUwUUwPywsQhqF2uoe2CeYXI",
          "mode": "list",
          "cachedResultName": "AI Voice Agent Data Set",
          "cachedResultUrl": "https://docs.google.com/spreadsheets/d/1IRcNkemHx4SpUJ65uvrNUwUUwPywsQhqF2uoe2CeYXI/edit?usp=drivesdk"
        },
        "sheetName": {
          "__rl": true,
          "value": "gid=0",
          "mode": "list",
          "cachedResultName": "Sheet1",
          "cachedResultUrl": "https://docs.google.com/spreadsheets/d/1IRcNkemHx4SpUJ65uvrNUwUUwPywsQhqF2uoe2CeYXI/edit#gid=0"
        },
        "columns": {
          "mappingMode": "defineBelow",
          "value": {
            "Order Type": "={{ $json.body.order_type }}",
            "Customer Name": "={{ $json.body.customer_name }}",
            "Phone": "={{ $json.body.phone }}",
            "Delivery Address": "={{ $json.body.delivery_address }}",
            "Order Date": "={{ $json.body.order_date }}",
            "Payment Method": "={{ $json.body.payment_method }}",
            "Order Status": "={{ $json.body.order_status }}",
            "Estimated Delivery Time": "={{ $json.body.estimated_delivery_time }}",
            "Sale Price": "={{ $json.body.sale_price }}",
            "Special Instructions": "={{ $json.body.special_instructions }}",
            "Delivery Status": "={{ $json.body.delivery_status }}",
            "Assigned Driver": "={{ $json.body.assigned_driver }}",
            "Food Items": "={{ $json.body.food_items }}"
          },
          "matchingColumns": [],
          "schema": [
            {
              "id": "Order ID",
              "displayName": "Order ID",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true,
              "removed": true
            },
            {
              "id": "Customer Name",
              "displayName": "Customer Name",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            },
            {
              "id": "Phone",
              "displayName": "Phone",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            },
            {
              "id": "Delivery Address",
              "displayName": "Delivery Address",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            },
            {
              "id": "Order Date",
              "displayName": "Order Date",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            },
            {
              "id": "Order Type",
              "displayName": "Order Type",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            },
            {
              "id": "Food Items",
              "displayName": "Food Items",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            },
            {
              "id": "Special Instructions",
              "displayName": "Special Instructions",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            },
            {
              "id": "Sale Price",
              "displayName": "Sale Price",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            },
            {
              "id": "Payment Method",
              "displayName": "Payment Method",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            },
            {
              "id": "Order Status",
              "displayName": "Order Status",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            },
            {
              "id": "Estimated Delivery Time",
              "displayName": "Estimated Delivery Time",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            },
            {
              "id": "Assigned Driver",
              "displayName": "Assigned Driver",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            },
            {
              "id": "Delivery Status",
              "displayName": "Delivery Status",
              "required": false,
              "defaultMatch": false,
              "display": true,
              "type": "string",
              "canBeUsedToMatch": true
            }
          ],
          "attemptToConvertTypes": false,
          "convertFieldsToString": false
        },
        "options": {}
      },
      "id": "96675512-6505-469c-9014-7af289fed5c8",
      "name": "AI voice agent Bilal",
      "type": "n8n-nodes-base.googleSheets",
      "typeVersion": 4,
      "position": [
        160,
        -120
      ],
      "credentials": {
        "googleSheetsOAuth2Api": {
          "id": "mPkBIZjnYeuKPQzw",
          "name": "Google Sheets account"
        }
      }
    },
    {
      "parameters": {
        "assignments": {
          "assignments": [
            {
              "id": "647f4281-bc54-456e-bf16-ac802ab4e862",
              "name": "body.customer_name",
              "value": " Bilal",
              "type": "string"
            },
            {
              "id": "e1db9a0d-9b4f-42d5-ad00-08a2b6964473",
              "name": "body.phone",
              "value": "12345678",
              "type": "string"
            },
            {
              "id": "edc30d30-81a9-4c59-9ec2-ec0805cc1385",
              "name": "body.delivery_address",
              "value": " ABC Street G13, Islamabad",
              "type": "string"
            },
            {
              "id": "1427a417-d046-4d45-aaf4-2b62a6537be8",
              "name": "body.order_date",
              "value": "23-07-2025",
              "type": "string"
            },
            {
              "id": "f4baeaf0-5aca-4283-b04a-3c3b6eb44049",
              "name": "body.order_type",
              "value": "Delivery",
              "type": "string"
            },
            {
              "id": "f6bc7ab2-f439-4b93-ba1a-2108361b221b",
              "name": "body.food_items",
              "value": " 3 x Pasta, 2 x Chicken Steaks, 1 x Medium Coke",
              "type": "string"
            },
            {
              "id": "ffd4ccb3-8006-4747-a893-e11807a6dcd2",
              "name": "body.special_instructions",
              "value": "No special instructions",
              "type": "string"
            },
            {
              "id": "566ee229-6c6a-4095-b85e-8b2be69c4099",
              "name": "body.sale_price",
              "value": "0",
              "type": "string"
            },
            {
              "id": "16539211-74b5-4c56-ba99-4ec47157d198",
              "name": "body.payment_method",
              "value": "Cash on Delivery",
              "type": "string"
            },
            {
              "id": "215dfaad-c507-4f49-a1ce-9c5d44bfc88c",
              "name": "body.order_status",
              "value": "Confirmed",
              "type": "string"
            },
            {
              "id": "e2b9e82b-93f6-46ee-9b28-6d83e750d45b",
              "name": "body.estimated_delivery_time",
              "value": " N/A",
              "type": "string"
            },
            {
              "id": "b9318c0d-8971-40aa-9d42-ed2d5632592f",
              "name": "body.assigned_driver",
              "value": " N/A",
              "type": "string"
            },
            {
              "id": "47479ce1-6cd1-4fd4-9391-e5976b7822da",
              "name": "body.delivery_status",
              "value": " N/A",
              "type": "string"
            }
          ]
        },
        "options": {}
      },
      "type": "n8n-nodes-base.set",
      "typeVersion": 3.4,
      "position": [
        -60,
        -120
      ],
      "id": "ae3430a4-8f32-4215-8848-4d094fca9eea",
      "name": "Arrange Data1"
    },
    {
      "parameters": {
        "content": "Main Purpose\nThis automated workflow eliminates missed phone orders and streamlines restaurant operations by deploying an AI voice agent that handles customer calls 24/7, processes orders with perfect accuracy, and automatically updates order databases in real-time.\n",
        "height": 200,
        "width": 260,
        "color": 5
      },
      "type": "n8n-nodes-base.stickyNote",
      "typeVersion": 1,
      "position": [
        -700,
        -160
      ],
      "id": "ca7a8c4b-2407-44ca-a3d7-b837452dae23",
      "name": "Sticky Note"
    },
    {
      "parameters": {
        "content": "",
        "height": 200,
        "width": 1040,
        "color": 4
      },
      "type": "n8n-nodes-base.stickyNote",
      "typeVersion": 1,
      "position": [
        -420,
        -160
      ],
      "id": "6aaa747f-2e0f-408c-9d4c-4f4381705c0d",
      "name": "Sticky Note1"
    }
  ],
  "connections": {
    "Webhook": {
      "main": [
        [
          {
            "node": "Arrange Data1",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "AI voice agent Bilal": {
      "main": [
        [
          {
            "node": "Respond to Webhook",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "Arrange Data1": {
      "main": [
        [
          {
            "node": "AI voice agent Bilal",
            "type": "main",
            "index": 0
          }
        ]
      ]
    }
  },
  "pinData": {
    "Webhook": [
      {}
    ]
  },
  "meta": {
    "templateCredsSetupCompleted": true,
    "instanceId": "c9022fab5e98f888acca230e4dbcc338e09adfb5d320403903c6b819ba734e1d"
  }
}
