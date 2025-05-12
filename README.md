from zipfile import ZipFile

# Redefine file paths since the code environment was reset
image_path = "/mnt/data/hajj_umrah_travel_page.jpg"
html_path = "/mnt/data/index.html"
zip_path = "/mnt/data/simple_image_page.zip"

# Create a simple HTML file to display the image
html_img_only = f"""
<!DOCTYPE html>
<html lang="so">
<head>
    <meta charset="UTF-8">
    <title>Sawirka Adeegyada</title>
    <style>
        body {{
            margin: 0;
            padding: 0;
            background: #000;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }}
        img {{
            max-width: 100%;
            height: auto;
            border-radius: 10px;
        }}
    </style>
</head>
<body>
    <img src="hajj_umrah_travel_page.jpg" alt="Sawirka Adeegyada">
</body>
</html>
"""

# Save the HTML file
with open(html_path, "w", encoding="utf-8") as f:
    f.write(html_img_only)

# Create a ZIP file containing the image and HTML
with ZipFile(zip_path, 'w') as zipf:
    zipf.write(image_path, arcname="hajj_umrah_travel_page.jpg")
    zipf.write(html_path, arcname="index.html")

zip_path
