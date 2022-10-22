# Importing the base image.
FROM python:latest

# To launch your python code, you must import it into our image.
# Use the keyword 'COPY' to do that.
# The first parameter 'main.py' is the name of the file on the host.
# The second parameter '/' is the path where to put the file on the image.
COPY main.py /

# You need to define the command to launch when you run the image.
# Use the keyword 'CMD' to do that.
CMD [ "python", "./main.py" ]