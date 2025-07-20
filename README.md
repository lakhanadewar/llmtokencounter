# 🤖 LLM Token Calculator

A modern, responsive web application that calculates token counts and estimates costs for popular Large Language Models (LLMs). This tool helps developers and researchers estimate API costs and understand token usage across different models.

## ✨ Features

- **Real-time Token Calculation**: Instantly calculates tokens as you type
- **Multi-Model Support**: Supports 8 popular LLM models including GPT-4, Claude 3, Gemini Pro, and more
- **Cost Estimation**: Provides input cost estimates based on current API pricing
- **Responsive Design**: Beautiful, modern UI that works on all devices
- **Advanced Tokenization**: Uses hybrid calculation methods for improved accuracy
- **Interactive Animations**: Smooth counter animations and hover effects

## 🎯 Supported Models

- **OpenAI Models**:
  - GPT-4 (4.0 chars/token, $30/$60 per 1M tokens)
  - GPT-3.5 Turbo (4.0 chars/token, $0.50/$1.50 per 1M tokens)

- **Anthropic Models**:
  - Claude 3 Opus (3.8 chars/token, $15/$75 per 1M tokens)
  - Claude 3 Sonnet (3.8 chars/token, $3/$15 per 1M tokens)
  - Claude 3 Haiku (3.8 chars/token, $0.25/$1.25 per 1M tokens)

- **Google Models**:
  - Gemini Pro (4.2 chars/token, $0.50/$1.50 per 1M tokens)

- **Open Source Models**:
  - Llama 2 70B (4.5 chars/token, $0.90/$0.90 per 1M tokens)
  - Mistral 7B (4.3 chars/token, $0.25/$0.25 per 1M tokens)

## 🚀 Quick Start

### Option 1: Direct Usage
1. Download the `index.html` file
2. Open it in any modern web browser
3. Start typing in the text area to see token calculations

### Option 2: Local Server
```bash
# Using Python 3
python -m http.server 8000

# Using Node.js (if you have http-server installed)
npx http-server

# Using PHP
php -S localhost:8000
```

Then open `http://localhost:8000` in your browser.

## 🔧 How It Works

### Token Calculation Algorithm

The calculator uses a hybrid approach for improved accuracy:

1. **Character-Based Method (70% weight)**:
   - Text length ÷ Average characters per token for each model
   - Uses model-specific ratios based on their tokenization algorithms

2. **Word-Based Method (30% weight)**:
   - Word count × 1.3 (average word-to-token ratio)
   - Accounts for subword tokenization patterns

### Model-Specific Ratios

Each model has different tokenization characteristics:
- **GPT Models**: ~4.0 characters per token (tiktoken cl100k_base)
- **Claude Models**: ~3.8 characters per token (optimized tokenization)
- **Gemini Pro**: ~4.2 characters per token
- **Llama 2 70B**: ~4.5 characters per token
- **Mistral 7B**: ~4.3 characters per token

## 📊 Display Features

- **Average Tokens**: Weighted average across all supported models
- **Character Count**: Total characters in the input text
- **Word Count**: Number of words (whitespace-separated)
- **Chars/Token Ratio**: Average characters per token
- **Per-Model Breakdown**: Individual token counts and cost estimates for each model

## 💰 Cost Estimation

The tool provides input cost estimates based on current API pricing (as of the implementation date). Costs are calculated as:

```
Cost = (Token Count ÷ 1,000,000) × Price per 1M tokens
```

**Note**: These are estimates for input tokens only. Actual costs may vary based on:
- Output token usage
- Current API pricing
- Actual tokenizer implementation
- Special characters and formatting

## 🎨 Technical Features

- **Pure HTML/CSS/JavaScript**: No external dependencies
- **Responsive Design**: Works on desktop, tablet, and mobile devices
- **Modern CSS**: Uses CSS Grid, Flexbox, and CSS animations
- **Glassmorphism UI**: Modern design with backdrop filters and gradients
- **Smooth Animations**: Counter animations and hover effects
- **Cross-browser Compatible**: Works in all modern browsers

## 🔍 Use Cases

- **API Cost Planning**: Estimate costs before making API calls
- **Token Budget Management**: Stay within token limits for different models
- **Model Comparison**: Compare token efficiency across different models
- **Development Testing**: Test prompts and content before deployment
- **Research**: Analyze tokenization patterns across models

## ⚠️ Limitations

- **Estimates Only**: Actual token counts may vary from estimates
- **Input Tokens**: Cost calculations are for input tokens only
- **Static Pricing**: Prices are based on implementation date and may change
- **Simplified Tokenization**: Uses approximation rather than actual tokenizers

## 🤝 Contributing

This is a single-file application that's easy to modify and extend:

1. **Adding New Models**: Update the `modelData` object with new model information
2. **Improving Calculations**: Modify the `estimateTokens` function
3. **UI Enhancements**: Update the CSS styles or add new features
4. **Pricing Updates**: Update the cost information in the model data

## 📄 License

This project is open source and available under the MIT License.

## 🔗 Related Resources

- [OpenAI Tokenizer](https://platform.openai.com/tokenizer)
- [Anthropic API Documentation](https://docs.anthropic.com/)
- [Google AI Studio](https://aistudio.google.com/)

---

**Disclaimer**: Token counts and costs are estimates. Always refer to official API documentation and billing for accurate information.
