# Day-03
#!/bin/bash

# =============================================
# CSV & TSV FILE MANIPULATION IN TERMINAL (DEMO)
# =============================================

echo "1. WORKING WITH xyz.csv (COMMA-SEPARATED)"
echo "----------------------------------------"

# Create xyz.csv and populate with sample data
echo "Creating xyz.csv with sample data..."
cat > xyz.csv <<EOF
11,12,13,14,15
21,22,23,24,25
31,32,33,34,35
41,42,43,44,45
51,52,53,54,55
61,62,63,64,65
34,67,11,89,11
EOF

echo -e "\nFile contents:"
more xyz.csv

echo -e "\nExtract 1st column:"
awk -F ',' '{print $1}' xyz.csv

echo -e "\nNumber of columns:"
awk -F ',' '{print NF; exit}' xyz.csv

echo -e "\n3rd row:"
head -n3 xyz.csv | tail -n1

echo -e "\nRows containing '11':"
head -n7 xyz.csv | grep '11'

echo -e "\n\n2. WORKING WITH lmn.csv (TAB-SEPARATED)"
echo "----------------------------------------"

# Create lmn.csv with tab-separated data
echo "Creating lmn.csv with sample data..."
cat > lmn.csv <<EOF
12      67      89
34      56      89
23      45      67
66      88      99
33      55      44
56      78      12
EOF

echo -e "\nFile contents:"
more lmn.csv

echo -e "\nExtract 1st column (tab-delimited):"
cut -d $'\t' -f1 lmn.csv

echo -e "\n3rd row:"
head -n3 lmn.csv | tail -n1

echo -e "\nNumber of columns:"
awk -F '\t' '{print NF; exit}' lmn.csv

echo -e "\nRows containing '56':"
head -n6 lmn.csv | grep '56'

echo -e "\nCleaning up..."
rm xyz.csv lmn.csv
echo "Done!"
1. WORKING WITH xyz.csv (COMMA-SEPARATED)
----------------------------------------
File contents:
11,12,13,14,15
21,22,23,24,25
[...]

Extract 1st column:
11
21
31
[...]

2. WORKING WITH lmn.csv (TAB-SEPARATED)
----------------------------------------
File contents:
12      67      89
34      56      89
[...]
