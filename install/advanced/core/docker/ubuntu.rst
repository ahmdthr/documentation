1. Install the Docker and docker-compose packages on a Ubuntu host
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Docker Setup (First time only)
..............................

.. code-block:: shell

  sudo add-apt-repository universe
  sudo apt-get update -y
  sudo apt-get install -y git-core git-buildpackage debhelper devscripts
  sudo apt-get install -y apt-transport-https ca-certificates curl gnupg-agent software-properties-common

  sudo mkdir -p /etc/apt/keyrings
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

  echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

  sudo apt-get update -y
  sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-compose
  sudo apt autoremove --purge

  sudo usermod -aG docker geonode
  su geonode

