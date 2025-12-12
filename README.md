# Auto-perif-go
auto-perif-go project description
This is a cryptographic security protocol generation and testing tool written in Go, supporting a complete workflow for protocol processing, format conversion, and security verification.

## Features

- **Protocol Processing**: Converts free-text protocol descriptions provided by users into detailed and accurate specifications via the GPT model.
- **Vulnerability Checking**: Automatically detects security vulnerabilities and potential issues in protocols.
- **Format Conversion**: Supports conversion between multiple protocol formats (PDL, SPDL, ProVerif).
- **Security Verification**: Integrates the ProVerif tool for formal security verification of protocols.

## Usage

The program supports multiple running modes with the basic syntax:

```bash
./auto-perif-go.exe [mode]
```

### Supported Modes

#### 1. Protocol Processing Mode (Default)

```bash
./auto-perif-go.exe
# or
./auto-perif-go.exe process
```

- Reads the protocol description from input.txt
- Generates a detailed protocol specification
- Checks for protocol vulnerabilities
- Generates the final cryptographic security protocol
- Saves results to out.txt

#### 2. PDL Conversion Mode

```bash
./auto-perif-go.exe pdl
```

- Converts the processed protocol into PDL format
- Saves results to outpdl.txt

#### 3. SPDL Conversion Mode

```bash
./auto-perif-go.exe spdl
```

- Converts the PDL protocol into SPDL format
- Saves results to final.spdl

#### 4. Partial Processing Mode

```bash
./auto-perif-go.exe all
```

- Executes protocol processing first, then converts the result to PDL format

#### 5. Full Workflow Mode

```bash
./auto-perif-go.exe full
```

- Executes the complete workflow: Protocol Processing → PDL Conversion → SPDL Conversion

## File Descriptions

- 'input.txt': Input file for protocol descriptions
- 'out.txt': Protocol processing results
- 'outpdl.txt': PDL format conversion results
- 'final.spdl': SPDL format conversion results
- 'config.json': Configuration file


## Usage Examples

### Basic Workflow

1. **Prepare Input File**：Write the protocol description in input.txt

   ```
   This is a simple authentication protocol...
   ```

2. **Execute Full Workflow**：

   ```bash
   ./auto-perif-go.exe full
   ```

3. **View Results**：

   - `out.txt`: Processed detailed protocol specification
   - `outpdl.txt`: Protocol in PDL format
   - `final.spdl`: Protocol in SPDL format (compatible with Scyther analysis)

### Step-by-Step Execution Example

```bash
# Step 1: Process the original protocol description
./auto-perif-go.exe process

# Step 2: Convert to PDL format
./auto-perif-go.exe pdl

# Step 3: Convert to SPDL format
./auto-perif-go.exe spdl

```

## Notes

1. **Configuration File**: Ensure the API key and model configurations in config.json are correct.
2. **Input File**: input.txt must exist and contain a valid protocol description.
3. **Network Connection**: The program requires network access to call the GPT model API.
4. **File Permissions**: Ensure the program has read/write permissions for files in the current directory.

## Troubleshooting

- **Compilation Errors**: Check that the Go version is 1.21 or higher and all dependencies are correctly installed.
- **API Call Failures**: Verify network connectivity and API configuration settings.
- **File Reading Errors**: Ensure the input file exists and has a valid format.

