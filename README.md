# TurnoverTracker: AI-Powered Bank Customer Turnover Prediction

Welcome to TurnoverTracker, a web application designed to demonstrate the power of AI in the financial sector. This tool predicts the likelihood of a bank customer's turnover (i.e., closing their account) and provides clear, AI-driven explanations for those predictions.

The application is built using a modern web stack and leverages Google's Generative AI to make complex model outputs understandable.

## Features

- **Predictive Analysis**: Input key customer data points (like credit score, age, balance, etc.) to receive an immediate turnover prediction ('Stay' or 'Leave').
- **Conceptual ANN Model**: The prediction logic simulates the output of an Artificial Neural Network (ANN), providing a realistic basis for analysis.
- **AI-Powered Explanations**: Utilizes **Genkit** with the **Google Gemini** model to generate human-readable explanations, detailing which factors most influenced the turnover prediction.
- **Interactive UI**: A clean, responsive, and user-friendly interface built with **Next.js**, **React**, and **ShadCN UI** components.
- **Server-Side Logic**: Employs Next.js Server Actions for secure and efficient communication between the client and the AI backend.

## Tech Stack

- **Framework**: [Next.js](https://nextjs.org/) (with App Router)
- **Language**: [TypeScript](https://www.typescriptlang.org/)
- **UI Components**: [ShadCN UI](https://ui.shadcn.com/)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **AI Integration**: [Genkit](https://firebase.google.com/docs/genkit)
- **Generative Model**: [Google Gemini](https://deepmind.google/technologies/gemini/)
- **Schema Validation**: [Zod](https://zod.dev/)

## Getting Started

Follow these instructions to set up and run the project locally.

### Prerequisites

- [Node.js](https://nodejs.org/en) (v18 or later)
- `npm` or a compatible package manager

### 1. Installation

Clone the repository and install the required dependencies:

```bash
git clone <repository_url>
cd TurnoverTracker
npm install
```

### 2. Environment Setup

To use the AI explanation feature, you need a Google AI API key.

1.  Create a `.env` file in the root of the project.
2.  Add your API key to the file:

    ```env
    GOOGLE_API_KEY="your_google_api_key_here"
    ```

    You can obtain a key from the [Google AI Studio](https://aistudio.google.com/app/apikey).

### 3. Running the Application

Start the development server:

```bash
npm run dev
```

The application will be available at [http://localhost:9002](http://localhost:9002).

## How It Works

1.  **Home Page (`/`)**: A landing page that provides an overview of the project and its features.
2.  **Prediction Tool (`/predict`)**: The core of the application.
    - A user enters customer data into a form.
    - The form data is validated using a Zod schema.
    - A mock prediction (simulating an ANN output) is generated on the client-side.
    - The customer data and the mock prediction result are sent to a **Genkit flow** via a Next.js Server Action.
    - The Genkit flow uses a **prompt** engineered to ask the Gemini model to explain the prediction based on the provided data, in the context of bank customer turnover.
    - The AI-generated explanation is returned to the client and displayed in the UI.

## Project Structure

- `src/app/` - Contains the pages and layouts for the Next.js App Router.
- `src/components/` - Houses all the React components, including UI components from ShadCN and custom page components.
- `src/ai/` - The heart of the AI functionality.
  - `genkit.ts`: Initializes and configures Genkit.
  - `flows/`: Contains the Genkit flows that orchestrate calls to the AI model.
- `src/lib/` - Includes utility functions and server-side logic.
  - `actions.ts`: Defines the Next.js Server Actions used to trigger AI flows.
- `src/schemas/` - Defines the Zod schemas for validating data, such as the customer input form.
- `public/` - Static assets.
- `tailwind.config.ts` - Configuration file for Tailwind CSS.
# Turnover-Tracker
# curmprediction
