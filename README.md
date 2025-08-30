# PPT Generator 📊

A powerful AI-powered PowerPoint presentation generator that transforms your text into professional slide presentations using multiple AI providers.

## 🌟 Features

- **Multi-AI Provider Support**: Works with OpenAI GPT, Anthropic Claude, Google Gemini, and AI Pipe
- **Smart Content Organization**: Automatically structures your content into well-organized slides
- **Template Support**: Upload your own PowerPoint templates (.pptx/.potx) for consistent branding
- **Image Reuse**: Option to copy and reuse images from uploaded template slides
- **Customizable Slide Count**: Generate 1-40 slides based on your content needs
- **Modern Web Interface**: Clean, responsive UI with dark/light theme support
- **Fast Processing**: Optimized slide generation with retry mechanisms
- **Vercel Ready**: Pre-configured for easy deployment on Vercel

## 🚀 Quick Start

### Prerequisites

- Python 3.13 or higher
- API key for at least one supported AI provider:
  - OpenAI API key
  - Anthropic API key  
  - Google Gemini API key
  - AI Pipe token

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/abhinv11/ppt-generator.git
   cd ppt-generator
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the application**
   ```bash
   uvicorn app:app --reload
   ```

4. **Open your browser**
   Navigate to `http://localhost:8000` to access the application.

## 📋 Usage

### Basic Usage

1. **Enter Your Content**: Paste or type your text content (up to 60,000 characters)
2. **Choose AI Provider**: Select from OpenAI, Anthropic, Google Gemini, or AI Pipe
3. **Enter API Key**: Provide your API key for the selected provider
4. **Set Parameters** (optional):
   - Number of slides (1-40)
   - AI model selection
   - Additional guidance for content structure
5. **Upload Template** (optional): Upload a .pptx or .potx file as a template
6. **Generate**: Click generate to create your presentation

### Advanced Options

- **Custom Guidance**: Provide specific instructions for how you want your content structured
- **Template Reuse**: Enable image reuse to copy images from your template slides
- **Model Selection**: Choose specific AI models for different quality/speed trade-offs

## 🛠️ API Endpoints

### `GET /`
Serves the main web interface.

### `POST /generate`
Generates a PowerPoint presentation from text input.

**Parameters:**
- `text` (required): Input text content
- `provider` (required): AI provider ("openai", "aipipe", "anthropic", "gemini")
- `api_key` (required): API key for the selected provider
- `guidance` (optional): Additional instructions for content structure
- `model` (optional): Specific AI model to use
- `num_slides` (optional): Desired number of slides (1-40)
- `reuse_images` (optional): Whether to copy images from template
- `template` (optional): PowerPoint template file (.pptx/.potx)

**Response:**
Returns a generated PowerPoint file (.pptx) for download.

## 🔧 Configuration

### Environment Variables

While the app accepts API keys through the web interface, you can also set them as environment variables:

```bash
export OPENAI_API_KEY="your-openai-key"
export ANTHROPIC_API_KEY="your-anthropic-key"
export GOOGLE_API_KEY="your-google-key"
```

### Customization

#### Default Models
- OpenAI: `gpt-4o-mini`
- Anthropic: `claude-3-5-sonnet-latest`
- Google: `gemini-2.5-flash`

#### Limits
- Maximum text input: 60,000 characters
- Slide range: 1-40 slides
- Template size limit: 30 MB

## 🚀 Deployment

### Vercel Deployment

This project is pre-configured for Vercel deployment:

1. **Fork/Clone the repository**
2. **Connect to Vercel**
3. **Deploy** - The `vercel.json` configuration will handle the setup automatically

### Manual Deployment

For other platforms:

1. **Install dependencies**: `pip install -r requirements.txt`
2. **Set environment variables** for your AI API keys
3. **Run the FastAPI app**: `uvicorn app:app --host 0.0.0.0 --port 8000`

## 📁 Project Structure

```
├── app.py              # Main FastAPI application
├── index.html          # Frontend web interface
├── requirements.txt    # Python dependencies
├── pyproject.toml     # Project configuration
├── vercel.json        # Vercel deployment config
├── favicon.ico        # Application icon
└── README.md          # This file
```

## 🧰 Tech Stack

- **Backend**: FastAPI, Python 3.13+
- **AI Integration**: OpenAI, Anthropic, Google Gemini APIs
- **PowerPoint Generation**: python-pptx
- **Frontend**: HTML5, CSS3, JavaScript, Bootstrap 5
- **Deployment**: Vercel (configured)

## 📝 API Provider Setup

### OpenAI
1. Sign up at [OpenAI](https://platform.openai.com/)
2. Generate an API key
3. Use model: `gpt-4o-mini` (recommended) or `gpt-4`

### Anthropic (Claude)
1. Sign up at [Anthropic](https://console.anthropic.com/)
2. Generate an API key
3. Use model: `claude-3-5-sonnet-latest` (recommended)

### Google Gemini
1. Get API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Use model: `gemini-2.5-flash` (recommended)

### AI Pipe
1. Sign up at your AI Pipe provider
2. Get your access token
3. Configure the base URL in the application

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🐛 Issues & Support

If you encounter any issues or have questions:

1. Check the [Issues](https://github.com/abhinv11/ppt-generator/issues) page
2. Create a new issue with detailed information
3. Include error messages and steps to reproduce

## 🔄 Version History

- **v0.1.0**: Initial release with multi-provider AI support, template handling, and web interface

## 🙏 Acknowledgments

- Built with [FastAPI](https://fastapi.tiangolo.com/)
- PowerPoint generation powered by [python-pptx](https://python-pptx.readthedocs.io/)
- UI styled with [Bootstrap 5](https://getbootstrap.com/)
- Icons from [Font Awesome](https://fontawesome.com/)

---

**Made with ❤️ for creating better presentations faster**
