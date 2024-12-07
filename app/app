
import pandas as pd
import uuid
import os
from flask import Flask, render_template, request, send_from_directory

# create an instance of the flask application
app = Flask(__name__)

# Create a route on your app
@app.route("/", strict_slashes=False, methods=["GET"])
def index():
    return render_template("app.html")


@app.route('/convert_csv', methods=['POST'])
def convert_csv():
    print(request.form.get("inputeFileType"))
    file = request.files['file']
    inputFileType=request.form.get("inputeFileType")
    outputFileType=request.form.get("outputFileType")

    if inputFileType == 'csv':
        df = pd.read_csv(file)
    elif inputFileType == 'xlsx':
        df = pd.read_excel(file)
    else:
        df = pd.read_json(file)

    if not os.path.exists('downloads'):
        os.makedirs('downloads')
    
    filename = f'{uuid.uuid4()}.{outputFileType}'
    output_file = os.path.join("downloads", filename)
    
    if outputFileType == 'csv':
        df.to_csv(output_file, index=False)
    elif outputFileType == 'xlsx':
        df.to_excel(output_file, index=False)
    elif outputFileType == 'json':
        df.to_json(output_file, orient='records')

    return render_template('download.html',filename=filename, outputFileType = outputFileType)


@app.route("/download/<filename>/<outputFileType>")
def download(filename, outputFileType):
    downloads_dir = os.path.abspath("downloads")
    download_name = f"result.{outputFileType}"
    if(outputFileType=='json'):
        return send_from_directory(
        directory=downloads_dir,  # Folder name where the file is stored
        path=filename,  # File to serve
        download_name= download_name, # Name to present to the user
        mimetype='application/octet-stream'
    )

    return send_from_directory(
        directory=downloads_dir,  # Folder name where the file is stored
        path=filename,  # File to serve
        download_name= download_name # Name to present to the user
    )



if __name__ == "__main__":
    app.run(debug="True")