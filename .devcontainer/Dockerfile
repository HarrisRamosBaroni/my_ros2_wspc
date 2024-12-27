FROM althack/ros2:humble-gazebo 

# ** [Optional] Uncomment this section to install additional packages. **
#
# ENV DEBIAN_FRONTEND=noninteractive
# RUN apt-get update \
#    && apt-get -y install --no-install-recommends <your-package-list-here> \
#    #
#    # Clean up
#    && apt-get autoremove -y \
#    && apt-get clean -y \
#    && rm -rf /var/lib/apt/lists/*
# ENV DEBIAN_FRONTEND=dialog

# Set up auto-source of workspace for ros user
ARG WORKSPACE
RUN echo "if [ -f ${WORKSPACE}/install/setup.bash ]; then source ${WORKSPACE}/install/setup.bash; fi" >> /home/ros/.bashrc

# Add the new commands to .bashrc
RUN echo "export XDG_RUNTIME_DIR=/tmp/runtime-ros" >> /home/ros/.bashrc && \
    echo "mkdir -p \$XDG_RUNTIME_DIR" >> /home/ros/.bashrc && \
    echo "chmod 700 \$XDG_RUNTIME_DIR" >> /home/ros/.bashrc
