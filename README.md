# svg-to-turtle

Draws SVG images with Python's `turtle` module. It reads the vector paths from an SVG file, turns each curve into points, and has the turtle trace and fill the shapes.

## What it does

- Loads an SVG with `svgpathtools` and reads its `viewBox` to scale the drawing window
- Splits each path into continuous sub-paths and samples points along every segment (every 5 units)
- Draws and fills each shape with turtle, using high tracer settings so large drawings render quickly
- Comes with sample SVGs in `all_svgs/` (mandalas, snowflakes, gnomes, Christmas designs)

## Tech

Python, svgpathtools, NumPy, turtle (standard library)

## Running it

```bash
pip install svgpathtools numpy
python main.py
```

To draw a different image, change `svg_file` at the top of `main.py`. The default path uses Windows-style backslashes (`all_svgs\mandalas\Mandala5.svg`), so on macOS or Linux change it to forward slashes.

## Notes

- Shapes are always filled in black. The script reads the SVG's style blocks, but it does not use the colours yet.
- Inspired by this project: https://www.reddit.com/r/Python/comments/fohqxy/made_a_program_that_reads_svg_files_and_draws_it/ (the original is more complicated, uses sprites and needs the SVG to be in a specific format).
- Personal learning project (December 2021).
