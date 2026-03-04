# Rejection as a Service (RaaS)
<a href="https://hits.sh/github.com/sapthesh/rejection-as-a-service/"><img alt="Hits" src="https://hits.sh/github.com/sapthesh/rejection-as-a-service.svg?view=today-total&style=for-the-badge&color=fe7d37"/></a>

Rejection as a Service is a humorous API and web interface designed to provide realistic, funny, and creative excuses for rejecting someone or something. Whether you need a polite "no," a bizarre reason, or just a good laugh, RaaS has you covered.

## Features

-   **Random Rejection Generator**: Get a unique excuse every time you hit the API.
-   **Modern UI**: A sleek, dark-mode interface built with React and Tailwind CSS.
-   **Clipboard Support**: Easily copy excuses to your clipboard with a single click.
-   **API Access**: Simple REST API endpoint to integrate rejections into your own applications.
-   **Responsive Design**: Works seamlessly on desktop and mobile devices.

## Tech Stack

-   **Frontend**: React, Vite, Tailwind CSS, Framer Motion (motion/react), Lucide React
-   **Backend**: Express.js
-   **Language**: TypeScript

## Getting Started

### Prerequisites

-   Node.js (v18 or higher)
-   npm (v9 or higher)

### Installation

1.  Clone the repository:
    ```bash
    git clone https://github.com/sapthesh/rejection-as-a-service.git
    cd rejection-as-a-service
    ```

2.  Install dependencies:
    ```bash
    npm install
    ```

3.  Start the development server:
    ```bash
    npm run dev
    ```

4.  Open your browser and navigate to `http://localhost:3000`.

## API Usage

### Get a Random Rejection

Retrieves a single, random rejection message.

**Endpoint**: `GET /api/v1/rejection`

**Parameters**: None

**Response**:

```json
{
  "rejection": "I'm focusing on my career as a professional cat herder right now.",
  "id": 42,
  "timestamp": "2024-03-14T10:00:00.000Z"
}
```

**Example Request (cURL)**:

```bash
curl -X GET http://localhost:3000/api/v1/rejection
```

**Example Request (JavaScript/Fetch)**:

```javascript
fetch('http://localhost:3000/api/v1/rejection')
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error('There was a problem with your fetch operation:', error));
```

**Example Request (Python/Requests)**:

```python
import requests

try:
    response = requests.get('http://localhost:3000/api/v1/rejection')
    response.raise_for_status()
    data = response.json()
    print(data)
except requests.exceptions.RequestException as e:
    print(f"Error: {e}")
```

**Example Request (Node.js/Axios)**:

```javascript
const axios = require('axios');

axios.get('http://localhost:3000/api/v1/rejection')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error('Error fetching rejection:', error);
  });
```

**Example Request (Go)**:

```go
package main

import (
	"encoding/json"
	"fmt"
	"io/ioutil"
	"net/http"
)

func main() {
	resp, err := http.Get("http://localhost:3000/api/v1/rejection")
	if err != nil {
		fmt.Println("Error:", err)
		return
	}
	defer resp.Body.Close()

	body, err := ioutil.ReadAll(resp.Body)
	if err != nil {
		fmt.Println("Error reading body:", err)
		return
	}

	var result map[string]interface{}
	json.Unmarshal(body, &result)
	fmt.Println(result)
}
```

**Status Codes**:

-   `200 OK`: Request successful. Returns a JSON object with the rejection message.
-   `404 Not Found`: The requested endpoint does not exist.
-   `500 Internal Server Error`: Something went wrong on the server side.

**Error Response Example**:

```json
{
  "error": "API endpoint not found"
}
```

## Contributing

We welcome contributions! If you have a funny excuse or a new feature idea, feel free to open an issue or submit a pull request.

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/amazing-excuse`).
3.  Commit your changes (`git commit -m 'Add amazing excuse'`).
4.  Push to the branch (`git push origin feature/amazing-excuse`).
5.  Open a Pull Request.

## License

This project is licensed under the Apache-2.0 License.

## Acknowledgments

-   Inspired by the universal human experience of needing a good excuse.

*Built with love (and a little bit of avoidance) by the Sapthesh V.*
