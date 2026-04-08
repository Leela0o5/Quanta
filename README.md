# Software Requirements Specification (SRS)

## 1. Overview

This project is a referral-based campaign platform where advertisers can create campaigns, users can share referral links, and rewards are distributed automatically.

The system uses blockchain (Solana) for tracking and payouts, but the experience should feel simple like a normal app.

---

## 2. System Goals

- Allow advertisers to create and fund campaigns  
- Enable users/creators to share referral links  
- Track clicks and conversions in real time  
- Distribute rewards instantly and transparently  
- Keep onboarding simple (even for non-crypto users)  

---

## 3. User Roles

### 3.1 Advertiser
- Creates campaigns  
- Funds campaigns  
- Tracks performance  

### 3.2 Creator / Referrer
- Generates referral links  
- Shares links  
- Earns rewards  

### 3.3 End User
- Clicks links  
- Claims rewards  

---

## 4. Functional Requirements

### 4.1 Authentication
- Users should be able to log in using email/password  
- Option to log in using Google  
- System should handle sessions securely  

---

### 4.2 Campaign Management
- Advertiser can:
  - Create a campaign  
  - Set total budget  
  - Set cost per click  
- Campaign data should be stored and retrievable  

---

### 4.3 Smart Contract Funding
- Advertiser deposits funds (SOL) into a smart contract  
- Funds are escrowed securely  
- System ensures:
  - Budget > cost per click  
  - No overspending  

---

### 4.4 Link Generation (Blink)
- System generates a unique campaign link  
- Link contains:
  - Campaign ID  
  - Smart contract reference  
- Link should work across platforms (X, Discord, etc.)  

---

### 4.5 Referral System
- Creators can generate referral links  
- Each link includes a unique identifier (wallet ID)  
- System tracks:
  - Who shared the link  
  - Who clicked it  

---

### 4.6 Tracking & Analytics
- System tracks:
  - Clicks  
  - Conversions  
  - Budget usage  
- Only valid (verified) interactions are counted  
- Dashboard shows:
  - Total clicks  
  - Remaining budget  
  - Amount spent  

---

### 4.7 Real-Time Updates
- Analytics should update in real time  
- Campaign stops automatically when budget is exhausted  

---

### 4.8 Rewards System
- Rewards are distributed per click or action  
- Reward split:
  - Portion to user  
  - Portion to referrer  
- Distribution happens automatically via smart contract  

---

### 4.9 Instant Payouts
- Rewards are sent instantly to wallets  
- Transactions should be visible on-chain  
- No manual approval required  

---

### 4.10 Reward Claiming
- User clicks “Claim Reward”  
- System triggers wallet signature  
- After claiming:
  - Reward is transferred  
  - UI updates  
  - Double claims are prevented  

---

### 4.11 Data Export
- Users can export data as CSV  
- Export should include:
  - Campaign data  
  - Referral data  
  - Performance metrics  

---

### 4.12 Wallet Abstraction (Onboarding)
- Users can sign in with Google  
- Wallet is created automatically in background  
- User does not need to understand crypto  
- Rewards still go to their wallet  

---

## 5. Non-Functional Requirements

### 5.1 Performance
- Dashboard should load quickly  
- Real-time updates should not lag  

### 5.2 Security
- Smart contracts must be secure  
- No double spending or double claiming  
- User data must be protected  

### 5.3 Scalability
- System should handle many campaigns and users  
- Should scale as usage grows  

### 5.4 Usability
- UI should be simple and clear  
- No complex crypto steps for normal users  

---

## 6. System Flow (High Level)

1. Advertiser creates campaign  
2. Advertiser funds campaign  
3. System generates campaign link  
4. Creator attaches referral ID  
5. Link is shared  
6. User clicks link  
7. Action is verified  
8. Reward is split and distributed  
9. Data is updated in dashboard  

---

## 7. Constraints

- Must use Solana for payments  
- Smart contract handles fund distribution  
- System depends on on-chain verification  

---

## 8. Future Improvements (Optional)

- More analytics features  
- Better fraud detection  
- Campaign customization options  
- Multi-chain support  
