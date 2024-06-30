# Firebase Data定義

```JSON
{
  "users": {
    "user_id": {
      "name": "string",
      "npub": "string",
      "loginMethods": {
        "method_id": {
          "type": "string",  // (例: "Google", "NIP-07")
          "details": "string"  // (例: "google@example.com")
        }
      },
      "linkedAccounts": {
        "account_id": {
          "service": "string",  // (例: "Twitter", "Facebook")
          "accountDetails": "string"  // (例: "@exampleUser")
        }
      },
      "profileKind": "integer",
      "log": {
        "log_id": {
          "timestamp": "timestamp",
          "action": "string"
        }
      },
      "sentCount": "integer",
      "totalPoints": "integer",
      "sentRatio": "float",
      "individualShare": "float",
      "averageShare": "float",
      "statistics": {
        "stat_id": {
          "statType": "string",  // (例: "daily", "monthly")
          "pointsSent": "integer",
          "pointsReceived": "integer",
          "timestamp": "timestamp"
        }
      }
    }
  },
  "temporaryUsers": {
    "temporary_user_id": {
      "tempId": "string",
      "expirationDate": "timestamp",
      "createdAt": "timestamp",
      "points": "integer",
      "log": {
        "log_id": {
          "timestamp": "timestamp",
          "action": "string"
        }
      },
      "statistics": {
        "stat_id": {
          "statType": "string",  // (例: "daily", "monthly")
          "pointsSent": "integer",
          "pointsReceived": "integer",
          "timestamp": "timestamp"
        }
      },
      "temporaryPoints": {
        "temp_point_id": {
          "points": "integer",
          "timestamp": "timestamp",
          "expirationDate": "timestamp"
        }
      }
    }
  },
  "points": {
    "point_id": {
      "senderId": "string",  // (users または temporaryUsers への参照)
      "receiverId": "string",  // (users または temporaryUsers への参照)
      "points": "integer",
      "timestamp": "timestamp",
      "expirationDate": "timestamp",
      "transactionType": "string"  // (例: "sent", "received")
    }
  },
  "log": {
    "log_id": {
      "userId": "string",  // (users への参照)
      "timestamp": "timestamp",
      "action": "string",
      "details": "string"  // (追加情報のためのオプションフィールド)
    }
  },
  "topPage": {
    "ranking_id": {
      "shareRanking": [
        {
          "userId": "string",  // (users への参照)
          "share": "float"
        }
      ],
      "sentCountRanking": [
        {
          "userId": "string",  // (users への参照)
          "count": "integer"
        }
      ],
      "userSearch": [
        {
          "userId": "string",  // (users への参照)
          "name": "string",
          "npub": "string"
        }
      ]
    }
  }
}

```
