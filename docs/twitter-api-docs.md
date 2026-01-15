# Twitter API Documentation (twitterapi.io)

> **Official Documentation:** https://docs.twitterapi.io/
> 
> **Purpose:** This is the Twitter API provider we use for all Twitter-related projects. Reference this document when building any Twitter integration.

---

## Overview

**Provider:** [twitterapi.io](https://docs.twitterapi.io/) (Kaito Twitter API)

**Key Features:**
- **Stability:** Proven with over 1,000,000+ API calls
- **Performance:** Average response time of 700ms
- **High QPS:** Supports up to 200 QPS per client
- **RESTful API:** Standard OpenAPI specifications
- **Cost-effective:** 96% cheaper than official Twitter API

---

## Pricing

| Data Type | Cost |
|-----------|------|
| Tweets | $0.15 per 1,000 tweets |
| User Profiles | $0.18 per 1,000 profiles |
| Followers | $0.15 per 1,000 followers |
| Minimum Charge | $0.00015 per request (even if no data returned) |

**Special Offer:** Discounted rates for students and research institutions 🎓

---

## Authentication

**Base URL:** `https://api.twitterapi.io`

**Authentication Method:** API Key in header

```javascript
const headers = {
  'X-API-Key': process.env.TWITTER_API_KEY,
  'Content-Type': 'application/json'
};
```

**Environment Variable:**
```bash
TWITTER_API_KEY=your_api_key_here
```

---

## API Endpoints Reference

### User Endpoints

| Method | Endpoint | Description | Documentation |
|--------|----------|-------------|---------------|
| GET | `/user/profile` | Get user profile about | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/user-endpoint/get-user-profile-about) |
| GET | `/user/batch` | Batch get user info by UserIds | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/user-endpoint/batch-get-user-info-by-userids) |
| GET | `/user/info` | Get user info | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/user-endpoint/get-user-info) |
| GET | `/user/tweets` | Get user's last tweets | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/user-endpoint/get-user-last-tweets) |
| GET | `/user/followers` | Get user followers | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/user-endpoint/get-user-followers) |
| GET | `/user/followings` | Get user followings | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/user-endpoint/get-user-followings) |
| GET | `/user/mentions` | Get user mentions | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/user-endpoint/get-user-mentions) |
| GET | `/user/check-follow` | Check follow relationship | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/user-endpoint/check-follow-relationship) |
| GET | `/user/search` | Search user by keyword | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/user-endpoint/search-user-by-keyword) |
| GET | `/user/verified-followers` | Get user verified followers | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/user-endpoint/get-user-verified-followers) |

---

### Tweet Endpoints

| Method | Endpoint | Description | Documentation |
|--------|----------|-------------|---------------|
| GET | `/tweet/ids` | Get tweets by IDs | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/tweet-endpoint/get-tweets-by-ids) |
| GET | `/tweet/replies` | Get tweet replies | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/tweet-endpoint/get-tweet-replies) |
| GET | `/tweet/quotations` | Get tweet quotations | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/tweet-endpoint/get-tweet-quotations) |
| GET | `/tweet/retweeters` | Get tweet retweeters | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/tweet-endpoint/get-tweet-retweeters) |
| GET | `/tweet/thread` | Get tweet thread context | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/tweet-endpoint/get-tweet-thread-context) |
| GET | `/tweet/article` | Get article | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/tweet-endpoint/get-article) |
| GET | `/tweet/search` | Advanced search | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/tweet-endpoint/advanced-search) |

---

### List Endpoints

| Method | Endpoint | Description | Documentation |
|--------|----------|-------------|---------------|
| GET | `/list/followers` | Get list followers | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/list-endpoint/get-list-followers) |
| GET | `/list/members` | Get list members | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/list-endpoint/get-list-members) |

---

### Communities Endpoints

| Method | Endpoint | Description | Documentation |
|--------|----------|-------------|---------------|
| GET | `/community/info` | Get community info by ID | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/communities-endpoint/get-community-info-by-id) |
| GET | `/community/members` | Get community members | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/communities-endpoint/get-community-members) |
| GET | `/community/moderators` | Get community moderators | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/communities-endpoint/get-community-moderators) |
| GET | `/community/tweets` | Get community tweets | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/communities-endpoint/get-community-tweets) |
| GET | `/community/search` | Search tweets from all communities | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/communities-endpoint/search-tweets-from-all-community) |

---

### Trend Endpoints

| Method | Endpoint | Description | Documentation |
|--------|----------|-------------|---------------|
| GET | `/trends` | Get trends | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/trend-endpoint/get-trends) |

---

### Spaces Endpoints

| Method | Endpoint | Description | Documentation |
|--------|----------|-------------|---------------|
| GET | `/space/detail` | Get space detail | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/spaces-endpoint/get-space-detail) |

---

### My Account Endpoints

| Method | Endpoint | Description | Documentation |
|--------|----------|-------------|---------------|
| GET | `/my/account` | Get my account info | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/my-endpoint/get-my-account-info) |

---

### Post & Action Endpoints (V3)

> ⚠️ **Note:** These endpoints are for posting/actions and require authenticated accounts.

| Method | Endpoint | Description | Documentation |
|--------|----------|-------------|---------------|
| POST | `/v3/login` | Log in V3 | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/post-and-action-endpoint-v3/log-in-v3) |
| GET | `/v3/account` | Get account detail V3 | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/post-and-action-endpoint-v3/get-account-detail-v3) |
| DELETE | `/v3/account/cookie` | Remove account cookie V3 | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/post-and-action-endpoint-v3/remove-account-cookie-v3) |
| PUT | `/v3/profile` | Update profile V3 | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/post-and-action-endpoint-v3/update-profile-v3) |
| POST | `/v3/tweet` | Send tweet V3 | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/post-and-action-endpoint-v3/send-tweet-v3) |
| POST | `/v3/like` | Like tweet V3 | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/post-and-action-endpoint-v3/like-tweet-v3) |
| POST | `/v3/retweet` | Retweet V3 | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/post-and-action-endpoint-v3/retweet-v3) |

---

### Webhook/Websocket Filter Rules

| Method | Endpoint | Description | Documentation |
|--------|----------|-------------|---------------|
| POST | `/webhook/rule` | Add webhook/websocket tweet filter rule | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/webhook-websocket-filter-rule/add-webhook-websocket-tweet-filter-rule) |
| GET | `/webhook/rules` | Get all webhook/websocket tweet filter rules | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/webhook-websocket-filter-rule/get-all-test-webhook-websocket-tweet-filter-rules) |
| POST | `/webhook/rule/update` | Update webhook/websocket tweet filter rule | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/webhook-websocket-filter-rule/update-webhook-websocket-tweet-filter-rule) |
| DELETE | `/webhook/rule` | Delete webhook/websocket tweet filter rule | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/webhook-websocket-filter-rule/delete-webhook-websocket-tweet-filter-rule) |

---

### Stream/Monitor Endpoints

| Method | Endpoint | Description | Documentation |
|--------|----------|-------------|---------------|
| POST | `/stream/user/add` | Add a twitter user to monitor their tweets | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/stream-endpoint/add-a-twitter-user-to-monitor-his-tweets) |
| POST | `/stream/user/remove` | Remove a user from monitor list | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/stream-endpoint/remove-a-user-from-monitor-list) |
| GET | `/stream/users` | Get users to monitor tweets | [Docs](https://docs.twitterapi.io/twitter-api-endpoint/stream-endpoint/get-users-to-monitor-tweet) |

---

## Common Use Cases

### 1. Get User Profile

```javascript
const getUserProfile = async (username) => {
  const response = await fetch(`https://api.twitterapi.io/user/info?userName=${username}`, {
    headers: {
      'X-API-Key': process.env.TWITTER_API_KEY
    }
  });
  return response.json();
};
```

### 2. Search Tweets

```javascript
const searchTweets = async (query) => {
  const response = await fetch(`https://api.twitterapi.io/tweet/search?query=${encodeURIComponent(query)}`, {
    headers: {
      'X-API-Key': process.env.TWITTER_API_KEY
    }
  });
  return response.json();
};
```

### 3. Get User's Tweets

```javascript
const getUserTweets = async (userId) => {
  const response = await fetch(`https://api.twitterapi.io/user/tweets?userId=${userId}`, {
    headers: {
      'X-API-Key': process.env.TWITTER_API_KEY
    }
  });
  return response.json();
};
```

### 4. Get Followers

```javascript
const getFollowers = async (userId) => {
  const response = await fetch(`https://api.twitterapi.io/user/followers?userId=${userId}`, {
    headers: {
      'X-API-Key': process.env.TWITTER_API_KEY
    }
  });
  return response.json();
};
```

### 5. Monitor User Tweets (Real-time)

```javascript
// Add user to monitor list
const addUserToMonitor = async (userId) => {
  const response = await fetch('https://api.twitterapi.io/stream/user/add', {
    method: 'POST',
    headers: {
      'X-API-Key': process.env.TWITTER_API_KEY,
      'Content-Type': 'application/json'
    },
    body: JSON.stringify({ userId })
  });
  return response.json();
};
```

---

## API Wrapper Class (Recommended)

```javascript
class TwitterAPI {
  constructor(apiKey) {
    this.apiKey = apiKey;
    this.baseUrl = 'https://api.twitterapi.io';
  }

  async request(endpoint, options = {}) {
    const url = `${this.baseUrl}${endpoint}`;
    const response = await fetch(url, {
      ...options,
      headers: {
        'X-API-Key': this.apiKey,
        'Content-Type': 'application/json',
        ...options.headers
      }
    });
    
    if (!response.ok) {
      throw new Error(`Twitter API Error: ${response.status}`);
    }
    
    return response.json();
  }

  // User Methods
  async getUserInfo(username) {
    return this.request(`/user/info?userName=${username}`);
  }

  async getUserById(userId) {
    return this.request(`/user/info?userId=${userId}`);
  }

  async getUserTweets(userId, cursor = null) {
    const params = cursor ? `?userId=${userId}&cursor=${cursor}` : `?userId=${userId}`;
    return this.request(`/user/tweets${params}`);
  }

  async getFollowers(userId, cursor = null) {
    const params = cursor ? `?userId=${userId}&cursor=${cursor}` : `?userId=${userId}`;
    return this.request(`/user/followers${params}`);
  }

  async getFollowing(userId, cursor = null) {
    const params = cursor ? `?userId=${userId}&cursor=${cursor}` : `?userId=${userId}`;
    return this.request(`/user/followings${params}`);
  }

  async searchUsers(keyword) {
    return this.request(`/user/search?keyword=${encodeURIComponent(keyword)}`);
  }

  // Tweet Methods
  async getTweetById(tweetId) {
    return this.request(`/tweet/ids?ids=${tweetId}`);
  }

  async getTweetsByIds(tweetIds) {
    return this.request(`/tweet/ids?ids=${tweetIds.join(',')}`);
  }

  async getTweetReplies(tweetId, cursor = null) {
    const params = cursor ? `?tweetId=${tweetId}&cursor=${cursor}` : `?tweetId=${tweetId}`;
    return this.request(`/tweet/replies${params}`);
  }

  async searchTweets(query, options = {}) {
    const params = new URLSearchParams({ query, ...options });
    return this.request(`/tweet/search?${params}`);
  }

  // Trend Methods
  async getTrends() {
    return this.request('/trends');
  }

  // Community Methods
  async getCommunityInfo(communityId) {
    return this.request(`/community/info?communityId=${communityId}`);
  }

  async getCommunityTweets(communityId, cursor = null) {
    const params = cursor ? `?communityId=${communityId}&cursor=${cursor}` : `?communityId=${communityId}`;
    return this.request(`/community/tweets${params}`);
  }

  // Stream/Monitor Methods
  async addUserToMonitor(userId) {
    return this.request('/stream/user/add', {
      method: 'POST',
      body: JSON.stringify({ userId })
    });
  }

  async removeUserFromMonitor(userId) {
    return this.request('/stream/user/remove', {
      method: 'POST',
      body: JSON.stringify({ userId })
    });
  }

  async getMonitoredUsers() {
    return this.request('/stream/users');
  }
}

// Usage
const twitter = new TwitterAPI(process.env.TWITTER_API_KEY);
const user = await twitter.getUserInfo('elonmusk');
```

---

## Error Handling

| Status Code | Description | Resolution |
|-------------|-------------|------------|
| 400 | Bad Request | Check request parameters |
| 401 | Unauthorized | Verify API key |
| 404 | Not Found | Resource doesn't exist |
| 429 | Rate Limited | Implement backoff, wait and retry |
| 500 | Server Error | Retry with exponential backoff |

```javascript
const handleApiError = (error, statusCode) => {
  switch (statusCode) {
    case 401:
      console.error('Invalid API key. Check TWITTER_API_KEY.');
      break;
    case 429:
      console.warn('Rate limited. Implementing backoff...');
      // Implement exponential backoff
      break;
    case 404:
      console.warn('Resource not found.');
      break;
    default:
      console.error('API Error:', error);
  }
};
```

---

## Best Practices

1. **Rate Limiting:** Implement exponential backoff for 429 errors
2. **Pagination:** Use cursor-based pagination for large datasets
3. **Caching:** Cache user profiles and tweets to reduce API calls
4. **Batch Requests:** Use batch endpoints when fetching multiple items
5. **Error Handling:** Always handle API errors gracefully
6. **Monitoring:** Track API usage to manage costs

---

## Cost Estimation

| Operation | Calls/Month | Cost |
|-----------|-------------|------|
| User Profiles | 10,000 | $1.80 |
| Tweets | 50,000 | $7.50 |
| Followers | 20,000 | $3.00 |
| **Total** | **80,000** | **$12.30** |

---

## Quick Reference

### Environment Setup
```bash
# Add to .env
TWITTER_API_KEY=your_api_key_here
```

### Import and Initialize
```javascript
const twitter = new TwitterAPI(process.env.TWITTER_API_KEY);
```

### Common Operations
```javascript
// Get user
const user = await twitter.getUserInfo('username');

// Search tweets
const tweets = await twitter.searchTweets('keyword');

// Get followers
const followers = await twitter.getFollowers(userId);

// Get trends
const trends = await twitter.getTrends();
```

---

## Support

- **Telegram:** Available via docs site
- **Documentation:** https://docs.twitterapi.io/

---

*Last updated: 2026-01-15*
*Reference: https://docs.twitterapi.io/*
