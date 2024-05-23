# biiif-cli 👷✨📃

```
npm i biiif-cli -g
```

```
biiif folder -u http://example.com/folder
```

Uses [biiif](https://github.com/edsilv/biiif)

## Options

### `-u`

The url location of your published collection. All of the IIIF `id` properties are generated using this as the base url.

<!--
### `-g`

Generate thumbnails for images.
-->

### `-v`

Use this virtual name for the root directory instead of its actual one when generating urls.
<!--
### `-s`

Scaffolds the following files (if they don't already exist):
- `.gitignore` - ignores the `node_modules` folder
- `.nojekyll` - disables jekyll to allow folder names starting with an underscore to be served on github pages
- `netlify.toml` - adds an `Access-Control-Allow-Origin: *` header for netlify.com
- `index.html` - includes a file explorer to navigate and share the contents of your IIIF collection
- `README.md` - includes a link to index.html

It also creates the folder specified in the `folder` argument. 
-->

### Local Development

1. **Open Git Bash**: Launch Git Bash on your desktop.
2. **Install `biiif-cli`**: Execute the following command to install `biiif-cli` globally:
   ```bash
   npm install -g biiif-cli
   ```
3. **Install an HTTP Server**: Install an HTTP server to serve the generated files:
   ```bash
   npm install -g http-server
   ```

#### Running `biiif-cli`

1. **Navigate to Your Image Folder**: Move to the directory containing your image files. For this demo, we'll use a folder named `starry-night`.
   ```bash
   cd path/to/your/starry-night
   ```
2. **Run `biiif-cli`**: Execute the tool on your image folder, specifying a local URL with port 8080.
   ```bash
   biiif path/to/your/starry-night -u http://localhost:8080
   ```
   This command generates image tiles, a thumbnail, and an `index.json` file in the specified directory.

#### Viewing Generated Files

1. **Open VS Code**: Launch Visual Studio Code and open the `starry-night` folder.
2. **Review Generated Files**: Inspect the generated files, including the image tiles, thumbnail, and `index.json`.

## Adding Metadata

1. **Edit Metadata**: Open the `metadata.yml` file within the `starry-night` folder.
2. **Add Metadata Information**: Add or update the metadata as required.
   ```yaml
   title: "Starry Night"
   creator: "Vincent van Gogh"
   description: "A famous painting by Vincent van Gogh."
   date: "1889"
   ```
3. **Regenerate Files**: After editing the metadata, run the `biiif-cli` command again to apply the changes.
   ```bash
   biiif path/to/your/starry-night -u http://localhost:8080
   ```
# BIIIF-CLI: Simple Demo with Universal Viewer Integration

## Introduction
This guide provides a detailed demonstration of how to use the `biiif-cli` tool to generate and manage image tiles, thumbnails, and metadata, and then view the results using a locally hosted instance of Universal Viewer.

## Prerequisites
Ensure you have the following installed on your system:
- [Git Bash](https://gitforwindows.org/)
- [Node.js](https://nodejs.org/)
- [Visual Studio Code (VS Code)](https://code.visualstudio.com/)
- [Universal Viewer example files](https://github.com/UniversalViewer/universalviewer/wiki/UV-Examples)

## Installation

1. **Open Git Bash**: Launch Git Bash on your desktop.
2. **Install `biiif-cli`**: Execute the following command to install `biiif-cli` globally:
   ```bash
   npm install -g biiif-cli
   ```
3. **Install an HTTP Server**: Install an HTTP server to serve the generated files:
   ```bash
   npm install -g http-server
   ```

## Running `biiif-cli`

1. **Navigate to Your Image Folder**: Move to the directory containing your image files. For this demo, we'll use a folder named `starry-night`.
   ```bash
   cd path/to/your/starry-night
   ```
2. **Run `biiif-cli`**: Execute the tool on your image folder, specifying a local URL with port 8080.
   ```bash
   biiif path/to/your/starry-night -u http://localhost:8080
   ```
   This command generates image tiles, a thumbnail, and an `index.json` file in the specified directory.

## Viewing Generated Files

1. **Open VS Code**: Launch Visual Studio Code and open the `starry-night` folder.
2. **Review Generated Files**: Inspect the generated files, including the image tiles, thumbnail, and `index.json`.

#### Adding Metadata

1. **Edit Metadata**: Open the `metadata.yml` file within the `starry-night` folder.
2. **Add Metadata Information**: Add or update the metadata as required.
   ```yaml
   title: "Starry Night"
   creator: "Vincent van Gogh"
   description: "A famous painting by Vincent van Gogh."
   date: "1889"
   ```
3. **Regenerate Files**: After editing the metadata, run the `biiif-cli` command again to apply the changes.
   ```bash
   biiif path/to/your/starry-night -u http://localhost:8080
   ```

#### Viewing manifest in Browser

1. **Start HTTP Server for Generated Files**: Serve the `starry-night` folder using the HTTP server.
   ```bash
   http-server path/to/your/starry-night -p 8080
   ```
2. **Open Universal Viewer**: Launch your web browser and navigate to:
   ```
   http://localhost:8090
   ```
   This URL should now serve the Universal Viewer, displaying the IIIF manifest generated by `biiif-cli`.


#### Viewing in Browser

1. **Start HTTP Server**: Serve the folder using the HTTP server.
   ```bash
   http-server path/to/your/starry-night -p 8080
   ```
2. **Open Browser**: Launch Firefox or your preferred web browser and navigate to `http://localhost:8080`.
3. **Reload Page**: Refresh the page to see the updated manifest.



### Setting Up Universal Viewer to view the image

1. **Download Universal Viewer Example Files**: Visit the [UniversalViewer CDN Example](https://github.com/UniversalViewer/universalviewer/wiki/UV-Examples) and download the files provided in the CodeSandbox CDN example as a ZIP file. Extract the ZIP file to a folder on your local machine.

2. **Set Up Local HTTP Server for Universal Viewer**: Navigate to the folder where you extracted the Universal Viewer example files and start the HTTP server.

   **Using `http-server`**:
   ```bash
   cd path/to/your/extracted-folder
   http-server -p 8090
   ```

   **Using Python (for Python 3.x)**:
   ```bash
   cd path/to/your/extracted-folder
   python -m http.server 8090
   ```

   **Using Python (for Python 2.x)**:
   ```bash
   cd path/to/your/extracted-folder
   python -m SimpleHTTPServer 8090
   ```

3. **Configure Universal Viewer**: Open the `http://localhost:8090` URL and update the manifest URL to point to the manifest generated by `biiif-cli` (e.g., `http://localhost:8080/index.json`).

