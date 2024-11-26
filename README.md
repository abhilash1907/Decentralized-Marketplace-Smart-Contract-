📦 Decentralized Marketplace Smart Contract
Welcome to the Decentralized Marketplace smart contract! This contract allows users to list items for sale and purchase them in a decentralised manner, directly on the Ethereum blockchain. 🚀

✨ Features
List items for sale 🛒
Sellers can list their items by specifying a name and price.
Purchase items 💰
Buyers can purchase listed items by paying the exact price.
Secure Transactions 🔒
Funds are directly transferred from the buyer to the seller.
📜 Smart Contract Details
📂 Contract Name: DecentralizedMarketplace
🔍 Structs
Item
name: The name of the item (string).
price: The price of the item in Wei (uint256).
seller: The address of the seller (payable).
buyer: The address of the buyer (initially 0x0).
isSold: A boolean indicating whether the item has been sold.
🔗 Mappings
items
A mapping to store all listed items using their unique ID (uint256).
🔢 Public Variables
itemCount
Tracks the total number of items listed.
🚀 Functions
🛒 listItem(string memory _name, uint256 _price)
Description:
Allows a seller to list an item for sale.
Parameters:
_name: Name of the item.
_price: Price of the item (in Wei).
Requirements:
Price must be greater than zero.
Emits:
ItemListed(uint256 itemId, string name, uint256 price, address seller)
💰 purchaseItem(uint256 _itemId)
Description:
Enables a buyer to purchase an item by paying the exact price.
Parameters:
_itemId: The ID of the item to purchase.
Requirements:
The item must exist.
The item must not already be sold.
The buyer must not be the seller.
The payment must match the item's price.
Transfers:
The contract transfers the payment directly to the seller.
Emits:
ItemPurchased(uint256 itemId, string name, uint256 price, address seller, address buyer)
📡 Events
ItemListed
Emitted when a new item is listed for sale.
Arguments:

itemId: Unique ID of the item.
name: Name of the item.
price: Price of the item.
seller: Address of the seller.
ItemPurchased
Emitted when an item is purchased.
Arguments:

itemId: Unique ID of the item.
name: Name of the item.
price: Price of the item.
seller: Address of the seller.
buyer: Address of the buyer.
✅ How to Use
💻 Setting Up
Deploy the contract on your desired blockchain using tools like Remix IDE or Hardhat.
Make sure your wallet (e.g., MetaMask) is connected to the blockchain.
📖 Workflow
Seller:
Call listItem with the item's name and price to list an item.
Wait for buyers to purchase.
Buyer:
Call purchaseItem with the item's ID and send the exact price in Wei.
Ownership of the item is transferred to the buyer.
⚠️ Requirements & Limitations
Prices are specified in Wei (1 Ether = 10¹⁸ Wei).
Buyers must ensure the payment matches the listed price exactly.
Sellers cannot purchase their own items.
🛠️ Customisation
This contract is designed to be simple. Feel free to extend it with features like:

Adding descriptions or categories for items.
Allowing bids or auctions.
Implementing a dispute mechanism.
📝 License
This project is licensed under the MIT License.

🎉 Happy coding! 🎉
