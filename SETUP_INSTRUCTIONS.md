# Nexus Platform Setup Instructions

## 🚀 **Complete Real-time Web3 Social Platform Implementation**

I've successfully implemented all the requested features:

### ✅ **Features Implemented:**

1. **Real-time Database Integration**
   - Posts, likes, and comments are saved to MongoDB
   - Real-time updates using Socket.IO
   - Authentication-based content visibility

2. **MetaMask Authentication Visibility**
   - Non-MetaMask users see only off-chain posts
   - MetaMask users see all content (off-chain, blockchain, NFT)
   - Session upgrade from Google to MetaMask

3. **Blockchain Upload & NFT Conversion**
   - Upload posts to blockchain (anchor)
   - Convert posts to NFTs
   - Real-time blockchain transaction updates

4. **Socket.IO Real-time Features**
   - Live post updates
   - Real-time likes and comments
   - Live blockchain/NFT status updates
   - User presence indicators

## 🔧 **Environment Variables Required**

Create a `.env` file in the `backend` directory with these variables:

```env
# Database Configuration
MONGODB_URI=mongodb://localhost:27017/nexus
DB_NAME=nexus

# JWT Configuration
JWT_SECRET=
JWT_REFRESH_SECRET=verysecretagain
JWT_EXPIRES_IN=1d
JWT_REFRESH_EXPIRES_IN=7d

# Google OAuth Configuration (Get these from Google Cloud Console)
GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret

# Blockchain Configuration (Use testnet for development)
ETHEREUM_RPC_URL=https://sepolia.infura.io/v3/your-infura-project-id
PRIVATE_KEY=your-private-key-for-transactions
CONTRACT_ADDRESS=your-deployed-contract-address

# IPFS Configuration (Get these from Pinata)
PINATA_API_KEY=your-pinata-api-key
PINATA_SECRET_KEY=your-pinata-secret-key
IPFS_GATEWAY_URL=https://gateway.pinata.cloud/ipfs/

# Server Configuration
PORT=5000
NODE_ENV=development
CORS_ORIGIN=http://localhost:5173

# Socket.IO Configuration
SOCKET_CORS_ORIGIN=http://localhost:5173

# Rate Limiting
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100

# File Upload
MAX_FILE_SIZE=10485760
UPLOAD_PATH=./uploads
```

## 🛠 **Setup Steps:**

### 1. **Backend Setup:**
```bash
cd backend
npm install
# Create .env file with the variables above
npm run dev
```

### 2. **Frontend Setup:**
```bash
cd frontend
npm install
npm run dev
```

### 3. **Database Setup:**
- Install MongoDB locally or use MongoDB Atlas
- Update `MONGODB_URI` in `.env` file

### 4. **Blockchain Setup (Optional for testing):**
- Get Infura project ID from https://infura.io
- Deploy smart contracts to testnet
- Update blockchain configuration in `.env`

### 5. **IPFS Setup (Optional for testing):**
- Get API keys from https://pinata.cloud
- Update IPFS configuration in `.env`

## 🎯 **Key Features:**

### **Authentication-Based Content Visibility:**
- **Non-MetaMask users**: See only off-chain posts
- **MetaMask users**: See all content including blockchain/NFT posts
- **Session upgrade**: Google users can upgrade to MetaMask

### **Real-time Features:**
- Live post creation and updates
- Real-time likes and comments
- Live blockchain transaction updates
- User presence indicators

### **Content Graduation Path:**
- **Off-chain**: Regular posts in database
- **Anchored**: Posts uploaded to blockchain
- **Minted**: Posts converted to NFTs

### **Socket.IO Events:**
- `new_post`: New post created
- `post_liked`: Post liked/unliked
- `post_commented`: Comment added
- `post_uploaded_to_blockchain`: Post anchored
- `post_converted_to_nft`: Post minted as NFT

## 🔄 **API Endpoints:**

### **Posts:**
- `GET /api/posts` - Get posts with auth-based visibility
- `POST /api/posts` - Create new post
- `POST /api/posts/:id/like` - Like/unlike post
- `POST /api/posts/:id/comment` - Add comment
- `POST /api/posts/:id/upload-blockchain` - Upload to blockchain
- `POST /api/posts/:id/convert-nft` - Convert to NFT

### **Authentication:**
- `POST /api/auth/google` - Google OAuth
- `POST /api/auth/metamask` - MetaMask authentication
- `POST /api/auth/upgrade-session` - Upgrade to Web3 session

## 🎨 **Frontend Components:**

- **RealTimeFeed**: Live feed with Socket.IO integration
- **SocketContext**: Socket.IO connection management
- **PostCard**: Enhanced with graduation path, tips, reporting
- **SessionUpgradeModal**: Google to MetaMask upgrade
- **All existing components**: Communities, Marketplace, etc.

## 🚀 **Ready to Use:**

The platform now has:
- ✅ Real-time database integration
- ✅ Socket.IO for live updates
- ✅ Authentication-based content visibility
- ✅ Blockchain upload and NFT conversion
- ✅ Complete Web3 social media experience

**Start the servers and enjoy your fully functional Web3 social platform!** 🎉
