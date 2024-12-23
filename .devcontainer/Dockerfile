FROM mcr.microsoft.com/devcontainers/ruby

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends git 

ARG USERNAME=vscode
# ARG USER_UID=1000
# ARG USER_GID=$USER_UID

# RUN if ! id -u $USERNAME >/dev/null 2>&1; then \
#         getent passwd $USER_UID || USER_UID=$(awk -F: 'BEGIN{uid=1001} $3>=uid{uid=$3+1} END{print uid}' /etc/passwd) \

#         # Create the user
#         && groupadd --gid ${USER_GID} ${USERNAME} \
#         && useradd --uid ${USER_UID} --gid ${USER_GID} -m ${USERNAME} \
#     fi

# # # Create the user
# # RUN groupadd --gid $USER_GID $USERNAME \
# # && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME
#         #
#         # [Optional] Add sudo support. Omit if you don't need to install software after connecting.
#         # && apt-get update \
#         # && apt-get install -y sudo \
#         # && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
#         # && chmod 0440 /etc/sudoers.d/$USERNAME
    
#     # ********************************************************
#     # * Anything else you want to do like clean up goes here *
#     # ********************************************************
    
#     # [Optional] Set the default user. Omit if you want to keep the default as root.

RUN gem install rake

USER $USERNAME

WORKDIR /home/$USERNAME/.local

RUN mkdir -p src/mruby  && \
    cd src/mruby && \
    git clone https://github.com/mruby/mruby.git . && \
    git checkout 3.3.0  && \
    make
    # make && \
    # cp bin/* ../bin







