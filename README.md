# Currency Converter API

A Spring Boot-based REST API for currency conversion and retrieving exchange rates. This project leverages external exchange rate APIs to provide up-to-date currency data and enables conversion between different currencies.

---

## Features
- Fetch real-time exchange rates for a specified base currency.
- Convert an amount from one currency to another.
- Handles errors gracefully with appropriate responses for invalid inputs.

---

## Technologies Used
- **Backend:** Spring Boot
- **HTTP Client:** RestTemplate
- **Database:** H2 (In-Memory Database)
- **External API:** ExchangeRate-API (https://exchangerate-api.com)

---

## Prerequisites
1. **Java Development Kit (JDK):** Version 8 or higher.
2. **Maven:** Ensure Maven is installed for dependency management.
3. **API Key:** Obtain a free API key from [ExchangeRate-API](https://exchangerate-api.com).

---

## Setup and Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/username/currency-converter-api.git
   cd currency-converter-api
   ```

2. Update the API Key:
   - Open the `application.properties` file.
   - Replace the placeholder with your API key:
     ```properties
     api.key=YOUR_API_KEY_HERE
     ```

3. Build and run the application:
   ```bash
   mvn spring-boot:run
   ```

4. Access the API at:
   ```
   http://localhost:8080
   ```

---

## Project Structure
```
src/
├── main/
│   ├── java/
│   │   ├── com.currencyconverter.currencyconverter/
│   │   │   ├── Config/             # Configuration files (e.g., AppConfig.java)
│   │   │   ├── controller/         # REST controllers
│   │   │   ├── model/              # Data models (e.g., ConversionRequest, ConversionResponse)
│   │   │   ├── service/            # Business logic
│   │   └── resources/
│   │       ├── application.properties  # Application configuration
│   ├── test/                       # Unit tests
```

---

## Example Requests
### Fetch Exchange Rates
```bash
curl "http://localhost:8080/api/rates?base=USD"
```

### Convert Currency
```bash
curl -X POST -H "Content-Type: application/json" -d '{"from":"USD", "to":"INR", "amount":100}' "http://localhost:8080/api/convert"
```

---

## Troubleshooting
- **400 Bad Request:**
  - Ensure the `from` and `to` currencies are valid 3-letter currency codes.
  - Validate that the amount is greater than zero.
- **External API Issues:**
  - Verify your API key and base URL in the `application.properties` file.
  - Test the external API directly to ensure it’s functioning.

---

## Contributions
Contributions are welcome! Feel free to open issues or submit pull requests for enhancements or bug fixes.

---

## Contact
For questions or feedback, please contact:
- **Name:** Arvindh S V
- **Email:** arvindhsamy007@gmail.com
```

