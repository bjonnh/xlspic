#! /usr/bin/env python
# WTFPL license

import xlsxwriter
import imageio
import sys

if len(sys.argv) !=3:
    print("That's not how it works")
    sys.exit(404)

pict = imageio.imread(sys.argv[1])

workbook = xlsxwriter.Workbook(sys.argv[2])
worksheet = workbook.add_worksheet()

for i in range(0, pict.shape[0]):
    for j in range(0, pict.shape[1]):
        a = pict[i, j]
        col = '#%02x%02x%02x' % (a[0], a[1], a[2])
        format = workbook.add_format()
        format.set_bg_color(col)
        worksheet.write(i, j, '', format)
workbook.close()
