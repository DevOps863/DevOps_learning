FROM almalinux:8 
WORKDIR /app
# The WORKDIR instruction sets the working directory for any RUN, CMD, ENTRYPOINT, COPY and ADD instructions that follow it in the Dockerfile. 
# If the WORKDIR doesn't exist, it will be created even if it's not used in any subsequent Dockerfile instruction
COPY Dockerfile .
# The COPY instruction copies the files or directories from <src>(local) and adds them to the filesystem of the image at the path <dest>
# It will copy the files only from the current direcotry and it's subsequent directories.