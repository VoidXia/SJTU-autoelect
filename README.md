# SJTU-autoelect
![Language](https://img.shields.io/badge/Language-Python3-red.svg) ![License](https://img.shields.io/github/license/voidxia/SJTU-autoelect)

## Features

- Auto relogin when session expired.
- Refresh page periodically to check course availibility and auto elect designated course.
- Resolve course conflict correctly.

## Usage

- Download corresponding chromedriver from https://chromedriver.chromium.org/downloads and save it in `DRIVERS` folder. ( Check OS and Chrome version! )
- Set your username and password in `getcookie_inte.py`.
- Run `pip install -r requirements.txt`.
- Run `python autoelect.py $COURSE_TYPE $COURSE_CODE $COURSE_KEYWORD1 $COURSE_KEYWORD2`.

### Arguments

- `COURSE_TYPE`: Course type, `01` for "主修课程", `10` for "通识课".
- `COURSE_CODE`: Course code, e.g. `EE234`.
- `COURSE_KEYWORD1`: Course keyword 1, e.g. `张三`.
- `COURSE_KEYWORD2`: Course keyword 2 ( Optional ), e.g. `星期一第11-13节`.

Make sure the keywords you provided are sufficient to locate the exact course!


## Example

`python autoelect.py 01 EE234 张三`

## Notes

- This program is not intended to work when server payload is high. Thus, you should only use it to catch the seats which others has cancelled recently.
- Uncomment line `option.add_argument('--headless')` to hide the chrome window.
- Opening several processes concurrently is possible.
- For Windows users, you may need to rename `chromedriver.exe` into `chromedriver` and install tesseract with python support.

## Todos

- Add support for course election with priority.
- Optimize program logic.
- Send requests instead of emulating user behaviors.

