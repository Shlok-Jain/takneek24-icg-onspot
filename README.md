# Takneek 24
This is submission of Pool Nawabs for on-spot PS from ICG fir Takneek 2024
Duration of PS was 2.5 hours.

# Team Members
Y23:
1. Shlok Jain

Y24:
1. Pranesh
2. Austin
3. Parth

# Mindful Pick
In today’s consumer landscape, transparency and impact verification of everyday products, such as food,
cosmetics, and household cleaners, are crucial yet often overlooked aspects. These fast-moving consumer
goods (FMCGs), which dominate our daily lives, have significant implications for our health, environment,
animals etc.

Unfortunately, many mainstream FMCGs flooding the market are neither healthy nor eco-friendly, often con-
tributing to environmental degradation. Despite frequent reports on social media about the harmful effects
of these products, it is nearly impossible for consumers to keep track of such information when making purchasing decisions.

Mindful pick is a application which takes input from user as images and then instantly provides detailed
ratings and reviews from various sources.

### Requirement specifications
1. Mindful Pick can be used on the following operating systems:
   1. Microsoft Windows 11, 10, 8.1, 7 for x86-64 (64-bit) processor architecture
   2. Linux for x86-64 (64-bit) and ARMv8-A (64-bit) processor architectures with a glibc version greater or equal to 2.18
2. Minimum system requirements are: 1 GHz single-core processor, 2 GB of RAM, 10 GB of free disk space

### Instruction to run
This is intended to run on google colab
1. Import it on google colab
2. Run the first cell to install the required libraries
3. Run the second cell to open a terminal in the colab
Use follownig command to run ollama in background.
```bash
curl -fsSL https://ollama.com/install.sh | sh
```
This should be ran in the terminal
4. Then install llama3 in it.
```bash
ollama serve & ollama pull llama3
```
Note: It will will not install it in single run probably. You have to run it multiple times. Once llama3 is installed move ahead.
5. Run consecutive cells to generate final csv.

### What's Under the Hood
We are using easyocr to extract the text (company, product name) from the image.
Then we are using LLM to corrcte errors in spelling and removing unnecessary text from extracted OCR text (Usually there is a lot of other thing written on packing than actual product name).
Then we are using duckduckgo web scarpping to extract amazon reviews and ratings.
The we are using llama3 to summarize it and calculate average rating.
Finally we are giving some links to news articles related to the product which are also extracted using web scraping.