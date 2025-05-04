# LiveKit Starter

This project is a Python starter template for integrating with LiveKit and related APIs.

## Prerequisites

- Python 3.8 or higher
- [pip](https://pip.pypa.io/en/stable/)

## Setup

1. **Clone the repository**

   ```bash
   git clone <your-repo-url>
   cd livekit-starter
   ```

2. **Create and activate a virtual environment**

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Configure environment variables**

   Create a `.env` file in the project root with the following content:

   ```env
   DEEPGRAM_API_KEY=<Your Deepgram API Key>
   OPENAI_API_KEY=<Your OpenAI API Key>
   CARTESIA_API_KEY=<Your Cartesia API Key>
   LIVEKIT_API_KEY=<your API Key>
   LIVEKIT_API_SECRET=<your API Secret>
   LIVEKIT_URL=wss://myapp-avkm45va.livekit.cloud
   ```

## Running the Project

To run the main script:

```bash
python main.py console
```

## Notes
- Make sure your `.venv` and `.env` files are included in `.gitignore` and not committed to version control.
- Update the `requirements.txt` file as you add new dependencies.

## License

MIT (or specify your license)

## Terminal Commands

Below are useful terminal commands for managing SIP participants, trunks, and dispatch rules with LiveKit:

| Command | Description |
|---------|-------------|
| `lk sip participant create sip-participant.json` | Creates a SIP participant using the configuration in `sip-participant.json`. |
| `lk sip dispatch list` | Lists all SIP dispatch rules. |
| `lk sip inbound list inbound-list.json` | Lists all inbound SIP trunks and saves the output to `inbound-list.json`. |
| `lk sip inbound create inbound-trunk.json` | Creates an inbound SIP trunk using the configuration in `inbound-trunk.json`. |
| `lk sip outbound create outbound-trunk.json` | Creates an outbound SIP trunk using the configuration in `outbound-trunk.json`. |
| `lk sip dispatch create dispatch-rule.json` | Creates a SIP dispatch rule using the configuration in `dispatch-rule.json`. |
| `python main.py dev` | Runs the main Python script in development mode. |

### How to Execute

Run these commands in your terminal from the project root. For example:

```bash
lk sip participant create sip-participant.json
```

Make sure you have the required CLI tools (such as `lk`) installed and your environment variables configured in your `.env` file. 