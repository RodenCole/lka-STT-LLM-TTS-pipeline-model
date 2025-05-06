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

## Useful Links

These are useful links when I was working on this

-[Intro the Realtime API](https://openai.com/index/introducing-the-realtime-api/)
-[OpenAI and LiveKit Advance Voice Realtime API](https://blog.livekit.io/openai-livekit-partnership-advanced-voice-realtime-api/)
-[OpenAI and LiveKit Integration](https://docs.livekit.io/agents/integrations/openai/)
-[LiveKit AI Agents Telephony](https://docs.livekit.io/agents/start/telephony/)

## Running with Docker

You can build and run this project in a Docker container. Here are the steps:

### 1. Build the Docker Image

From the project root, run:

```bash
docker build -t my-livekit-agent .
```
- This command builds the Docker image and tags it as `my-livekit-agent`.

### 2. Run the Docker Container

```bash
docker run --rm -it --env-file .env -p 8081:8081 my-livekit-agent
```
- `--env-file .env` loads environment variables from your `.env` file.
- `-p 8081:8081` maps port 8081 from the container to your host (for health checks or other services).
- `--rm` removes the container after it stops.
- `-it` allows interactive mode (useful for logs and debugging).
- `my-livekit-agent` is the image name you built in the previous step.

**Note:**
- Make sure your `.env` file is present in your project root and contains all required environment variables.
- The application will be accessible on `localhost:8081` if it exposes a health check or web endpoint.