# CDRFontSearcher

## Overview
**CDRFontSearcher** is a PHP class designed to search for a specific font inside CorelDRAW (`.cdr`) files. It extracts and scans `pageX.dat` files within CDR archives (which are ZIP-compressed) to locate the specified font.

## Features
- Scans all `.cdr` files in a given directory.
- Searches for font names inside `pageX.dat` files.
- Extracts unique fonts found in each file.
- Works without requiring CorelDRAW to be installed.

## Requirements
- PHP 7.4 or later
- `ZipArchive` extension enabled in PHP

## Installation
1. Clone or download the script into your project directory.
2. Ensure PHP is installed and configured properly.
3. Verify that the `ZipArchive` extension is enabled in `php.ini`.

## Usage
### Example: Searching for a specific font
```php
require 'CDRFontSearcher.php';

$directory = '/path/to/cdr/files';
$searchFont = 'LetterOMatic!'; // Change to the font you want to search for

$fontSearcher = new CDRFontSearcher($directory, $searchFont);
$fontSearcher->search();
```

## Methods
### `__construct(string $directory, string $searchFont)`
- **`$directory`**: Path to the directory containing CDR files.
- **`$searchFont`**: The font name to search for.

### `search(): void`
Scans the directory and processes all `.cdr` files to find the specified font.

### `processCDRFile(string $cdrFile): void`
Handles the extraction and scanning of an individual CDR file.

### `containsFont(string $content): bool`
Checks if the extracted file content contains the specified font.

## Example Output
```
Searching for files with font 'LetterOMatic!' in CDR files...
Font 'LetterOMatic!' found in: example1.cdr
Font 'LetterOMatic!' found in: example2.cdr
```

## License
This project is open-source and available under the MIT License.

