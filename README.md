# Habitica To-Do Sorter

A vibe-coded utility to automate repetitive Habitica task sorting, using local storage to ensure your API credentials stay private on your machine while providing a zero-footprint daily summary.

## Live Tool

[**Access the Sorter Here**](https://leonampa.github.io/habitica-todo-sorter/)

## Technical Sorting Logic

The tool processes active To-Dos using a specific priority hierarchy:

* **Filtering:** Tasks beginning with special characters /, %, &, $ are ignored.

* **Priority (Exclamation Marks):** 

  * Tasks containing `!` are ranked by frequency. The more exclamation marks a task has, the higher it appears in the list.

  * If two tasks have the same number of `!` marks, the task with the greater character length is ranked higher.

  * Tasks without any `!` marks are sorted by character length in descending order.

## Features

* **Privacy-First:** User ID and API Token are stored strictly in `localStorage`. Data remains on your machine and is never transmitted to any third-party backend.

* **Target Date Automation:** Generates a "Tomorrow" summary by default. Support for advanced scheduling is provided via a `!^!` prefix:

  * **`!^!7`**: Sets the summary target to 7 days from now.

  * **`!^!`**: (No number) Targets the upcoming Monday.

  * *Note: Tasks used as scheduling triggers (containing `!^!`) are excluded from the sorted output.*

* **Greek Localization:** Date headers and summaries are generated in Greek (e.g., "Για αυριο Δευ 12 Ιαν").

## Usage

1. Provide your **User ID** and **API Token** (found in [Habitica.com](https://habitica.com/user/settings/siteData) > User > Settings > Site Data).

2. Execute **Fetch & Sort** to retrieve and organize your current To-Dos.

3. Review the preview and click **Save to Habitica** to create the bundled summary task.