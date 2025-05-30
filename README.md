# AI-FOR-SW-ENGINEERING-ASSIGNMENT-1-CHATBOT
crypto_db = {  
    "Bitcoin": {  
        "price_trend": "rising",  
        "market_cap": "high",  
        "energy_use": "high",  
        "sustainability_score": 3/10  
    },  
    "Ethereum": {  
        "price_trend": "stable",  
        "market_cap": "high",  
        "energy_use": "medium",  
        "sustainability_score": 6/10  
    },  
    "Cardano": {  
        "price_trend": "rising",  
        "market_cap": "medium",  
        "energy_use": "low",  
        "sustainability_score": 8/10  
    }  
}

def crypto_advice(user_query):
    user_query = user_query.lower()
    
    if "trending up" in user_query or "rising" in user_query:
        trending = [coin for coin, data in crypto_db.items() if data["price_trend"] == "rising"]
        return f"Trending cryptocurrencies: {', '.join(trending)} 📈"
    
    elif "most sustainable" in user_query or "eco-friendly" in user_query:
        recommend = max(crypto_db, key=lambda x: crypto_db[x]["sustainability_score"])
        return f"Invest in {recommend}! 🌱 It’s eco-friendly and has long-term potential."
    
    elif "long-term growth" in user_query:
        candidates = [coin for coin, data in crypto_db.items() if data["price_trend"] == "rising" and data["market_cap"] in ["high", "medium"]]
        return f"For long-term growth, consider: {', '.join(candidates)} 🚀"
    
    else:
        return "I can help with crypto trends and sustainability. Try asking about trending or eco-friendly coins!"

# Testing the function:
user_input = input("Ask CryptoBuddy: ")
print(crypto_advice(user_input))

testing results in terminal
PS C:\Users\User\Desktop\AI  FOR SW WEEK 1\CryptoBot> python crypto_bot.py
Ask CryptoBuddy: trending up
Trending cryptocurrencies: Bitcoin, Cardano 📈
