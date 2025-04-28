# Torrent-To-Google-Drive-Downloader-v4---Colab
# Google Colab Torrent Downloader to Google Drive (via aria2c)

This script allows you to download torrent files or use magnet links directly to your Google Drive using the power of a Google Colab notebook and the `aria2c` download utility.

---

**🚨 IMPORTANT WARNING & DISCLAIMER 🚨**

* **LEGAL USE ONLY:** This tool is provided for technical demonstration and convenience. **Only download content that you have the legal right to access and distribute.** Downloading copyrighted material without permission is illegal and violates Google's and GitHub's terms of service.
* **USER RESPONSIBILITY:** You are solely responsible for the content you download using this script. The author(s) of this repository are not responsible for any misuse of this tool or any consequences arising from such misuse.
* **RESOURCE USAGE:** Downloading large files consumes Google Colab resources (CPU, RAM, disk) and your Google Drive storage space. Ensure you have sufficient storage available in your Drive.
* **GOOGLE'S POLICIES:** Google may monitor Google Drive usage. Excessive or abusive activity, including storing infringing content, could lead to restrictions on your Google account. Use responsibly.

---

## Features

* Mounts your Google Drive within the Colab environment.
* Installs the `aria2c` command-line download utility.
* Downloads torrents using either magnet links or `.torrent` files.
* Saves downloaded files directly to a specified folder in your Google Drive.
* Provides cleaner, real-time download progress updates (Speed, ETA, Size).
* Configured to stop seeding immediately after download (`--seed-time=0`) to conserve resources.

## Requirements

* A Google Account (for Google Drive and Google Colab).
* A web browser to run Google Colab.

## How to Use

1.  **Obtain the Notebook:** Download the `.ipynb` file from this repository.
2.  **Open in Google Colab:**
    * Go to [Google Colab](https://colab.research.google.com/).
    * Click `File` -> `Upload notebook...` and select the downloaded `.ipynb` file.
3.  **Run Cell 1: Mount Google Drive:**
    * Execute the first code cell.
    * Follow the prompts to authorize Colab to access your Google Drive. Ensure it mounts successfully.
4.  **Run Cell 2: Install aria2c:**
    * Execute the second code cell. This will install the necessary download tool within the Colab environment for this session.
5.  **Configure and Run Cell 3: Download Torrent:**
    * **Crucially, edit the `source_input` variable:**
        * Replace `"YOUR_MAGNET_LINK_HERE"` with the actual magnet link you want to use.
        * *Alternatively*, if using a `.torrent` file:
            * Upload the `.torrent` file to your Colab session's file browser (left sidebar, folder icon) or to your Google Drive.
            * Comment out the magnet link line.
            * Uncomment the line `# source_input = '/content/your_file.torrent'` and replace `/content/your_file.torrent` with the correct path to your uploaded file (e.g., `/content/drive/MyDrive/my_torrent.torrent` if it's in Drive).
    * **(Optional) Modify `drive_save_folder`:** Change the value `'Torrents_aria2'` if you want to save downloads to a different folder name within your Google Drive's "My Drive". The script will create this folder if it doesn't exist.
    * Execute the third cell.
6.  **Monitor Download:** The cell will output the download progress. Wait for it to show "Download complete" or "aria2c finished successfully."
7.  **Access Files:** Check the specified save folder in your Google Drive for the downloaded content.

## Important Notes

* **Seeding:** This script is configured with `--seed-time=0` to stop seeding immediately after the download finishes. This is done to save Colab resources and potentially avoid issues with tracker communication from Colab's IPs.
* **Errors:** If `aria2c` exits with an error code, check the output log in Cell 3 for details. Common errors include invalid magnet links/torrent files, tracker issues, or lack of peers.
* **Session Lifetime:** Colab notebooks have time limits for execution and idle time. Very long downloads might be interrupted.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Feel free to open an issue if you find a bug or have a suggestion for improvement. Pull requests are also welcome.

