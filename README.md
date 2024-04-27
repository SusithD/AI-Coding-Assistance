# AI Coding Assistance with CodeLlama

Welcome to the AI Coding Assistance project with CodeLlama! This repository contains the necessary resources to set up and utilize CodeLlama for enhanced coding experiences. Below, you'll find detailed instructions on getting started, customizing models, and interacting with the CodeLlama environment.

### Getting Started

To begin using CodeLlama, follow these steps based on your operating system:

- **macOS**: Download the CodeLlama executable from the [macOS download page](https://ollama.com/download).
- **Windows**: Download the CodeLlama preview from the [Windows download page](https://ollama.com/download).
- **Linux**: Run the following command in your terminal:

    ```bash
    curl -fsSL https://ollama.com/install.sh | sh
    ```

### Docker

If you prefer using Docker, the official CodeLlama Docker image `ollama/ollama` is available on Docker Hub.

### Libraries

CodeLlama provides libraries for Python (`ollama-python`) and JavaScript (`ollama-js`), enabling seamless integration with your preferred programming language.

### Quickstart

To quickly run and chat with CodeLlama, execute the following command:

```bash
ollama run codellama
```

**Customizing a Model from GGUF**

CodeLlama supports importing GGUF (Great GPT Unified Framework) models, allowing you to customize and use them within your environment. Follow these steps to import and customize a GGUF model:

1. **Prepare the Modelfile**: Create a file named `Modelfile` and include a `FROM` instruction with the local filepath to the GGUF model you want to import. For example:

    ```plaintext
    FROM ./vicuna-33b.Q4_0.gguf
    ```

2. **Create the Model in CodeLlama**: Use the `ollama create` command, specifying the name of your model and the `Modelfile` as follows:

    ```bash
    ollama create example -f Modelfile
    ```

3. **Run the Model**: Once the model is created, you can run it using the `ollama run` command:

    ```bash
    ollama run example
    ```

By following these steps, you can import GGUF models into CodeLlama, customize them to suit your needs, and leverage their capabilities for various tasks and applications.

### Customizing a Prompt

You can customize models from the CodeLlama library using a prompt. For example, to customize the `codellama` model:

1. Pull the `codellama` model.
    ```bash
    ollama pull codellama
    ```

2. Create a `Modelfile` specifying the desired parameters and system message, then create and run the model.

    ```bash
    FROM codellama

    # Set the temperature to 1 [higher is more creative, lower is more coherent]
    PARAMETER temperature 1

    # Set the system message
    SYSTEM """
    You are a code teaching assistant named as The qexle Coder Created by Susith Deshan Alwis.Answer all programming related questions being asked.
    """
    ```

### CLI Reference

Below are some essential commands for managing and interacting with CodeLlama:

- **Create a Model**: Use `ollama create` to create a model from a `Modelfile`.
- **Pull a Model**: Use `ollama pull` to pull a model from the CodeLlama library or update a local model.
- **Remove a Model**: Use `ollama rm` to remove a model.
- **Copy a Model**: Use `ollama cp` to copy a model.
- **Multiline Input**: Wrap text with `"""` for multiline input.

### Building

If you want to build CodeLlama locally, follow these steps:

1. Install `cmake` and `go`.
    ```bash
    brew install cmake go
    ```

2. Generate dependencies and build the binary.
    ```bash
    go generate ./...
    go build .
    ```

3. Start the server and run a model.
    ```bash
    ./ollama serve
    ./ollama run llama3
    ```

### REST API

CodeLlama provides a REST API for running and managing models. Use the following endpoints to interact with the API:

- **Generate a Response**: `http://localhost:11434/api/generate`
- **Chat with a Model**: `http://localhost:11434/api/chat`

For detailed API usage, refer to the official documentation.

### Contributing

Contributions to the CodeLlama project are welcome! If you encounter any issues or have suggestions for improvements, feel free to open an issue or submit a pull request on GitHub.

---

Enjoy coding with CodeLlama! If you have any questions or need assistance, don't hesitate to reach out. Happy coding!
