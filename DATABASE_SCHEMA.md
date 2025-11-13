# Database Schema Status

## Available Tables ✅

### market.stocks
- `stock_id` (int)
- `symbol` (string)

### market.stock_quotes
- `quote_id` (int)
- `stock_id` (int)
- `timestamp` (datetime)
- `quote_type` (string)
- `bid` (float)
- `bid_size` (int)
- `ask` (float)
- `ask_size` (int)
- `mid` (float)
- `last` (float)

### market.stock_candles
- `stock_id` (int)
- `timestamp` (datetime)
- `resolution` (string)
- `open` (float)
- `high` (float)
- `low` (float)
- `close` (float)
- `day_volume` (int)

## Working Functions

✅ `get_stocks()` - Fetch stock symbols
✅ `get_stock_quotes()` - Fetch stock quotes
✅ `get_stock_candles()` - Fetch OHLCV candles
✅ `get_option_contracts()` - Fetch option contracts
✅ `get_option_quotes()` - Fetch option quotes

## Non-Working Functions

❌ `get_option_contracts()` - Requires `market.option_contract` table
❌ `get_option_quotes()` - Requires `market.option_quotes` and `market.option_contract` tables

## Notes

**The database schema only supports stock data.**

The SDK includes options functionality (`get_option_contracts()`, `get_option_quotes()`), but these functions cannot be used because the required database tables (`market.option_contract`, `market.option_quotes`) do not exist in your database schema.

**Recommendation:** Only use the stock-related functions:
- `get_stocks()`
- `get_stock_quotes()`
- `get_stock_candles()`
