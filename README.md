import requests

def get_bitcoin_price():
    url = 'https://api.coindesk.com/v1/bpi/currentprice.json'
    try:
        response = requests.get(url)
        response.raise_for_status()
        data = response.json()
        price = data['bpi']['USD']['rate']
        print(f"💰 Current Bitcoin Price: ${price}")
    except requests.exceptions.RequestException as e:
        print("Error fetching Bitcoin price:", e)

if __name__ == "__main__":
    get_bitcoin_price()
