# Database design

## Firebase Realtime Database

- can only use one
- keep it flat for easy lookups
- limits are based on bandwidth, not on read/writes

## Design thoughts

- separate concerns (pulls, settings, collection, etc)

### Use cases

#### Display collection

- all cards the user has pulled
- all cards the user hasn't pulled
- chronological order of pulls
- number of times a given card has been pulled

#### Display card details

- when card was pulled
- where it was pulled from (pack, store)

#### Example of potential structure

```json
{
  "users": {
    "user123": {
      "packPoints": 200,
      "lastView": "binder",
      "lastPack": "set_abc",
      "viewSettings": {
        "collection": {
          "sortBy": "id",
          "set": "set_abc",
          "gridRows": 3,
          "gridCols": 4
        },
        "binder": {
          "gridRows": 3,
          "gridCols": 3,
          "name": "Favorites"
        },
        "pull": {
          "skipClicking": true
        }
      }
    }
  },
  "pulls": {
    "user123": {
      "pull_1": {
        "cardId": "card123",
        "date": "2025-08-01T12:00:00Z",
        "source": "pack"
      },
      "pull_2": {
        "cardId": "card456",
        "date": "2025-08-02T09:00:00Z",
        "source": "shop"
      }
    }
  },
  "cardPullCounts": {
    "user123": {
      "card123": 5,
      "card456": 2
    }
  },
  "binders": {
    "user123": {
      "binder1": {
        "name": "Favorites",
        "cards": {
          "slot1": "card123",
          "slot2": "card456",
          "slot3": null
        }
      }
    }
  },
  "coins": {
    "user123": {
      "coin1": "2025-08-01T12:00:00Z"
    }
  }
}
```
