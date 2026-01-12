# langchain4j_ollama_graphaugment<br>
<br>
# dnf5<br>
# Docker<br>
sudo dnf config-manager addrepo --from-repofile=https://download.docker.com/linux/fedora/docker-ce.repo<br>
<br>
sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin<br>
sudo systemctl enable --now docker<br>
sudo docker run hello-world<br>
<br>
#sudo groupadd docker<br>
sudo usermod -aG docker $USER<br>
<br>
# cd tmp<br>
# wget -O docker-desktop-x86_64.rpm https://desktop.docker.com/linux/main/amd64/docker-desktop-x86_64.rpm?utm_source=docker&utm_medium=webreferral&utm_campaign=docs-driven-download-linux-amd64
# sudo dnf install ./docker-desktop-x86_64.rpm
<br>
Register on site and Download data from https://www.kaggle.com/c/h-and-m-personalized-fashion-recommendations/overview<br>
articles.csv.zip<br>
customers.csv.zip<br>
transactions_train.csv.zip<br>
<br>
Recommend using Podman Desktop and podman-compose.yml<br>
(Docker Desktop sometimes hangs on my laptop)<br>
<br>
sudo dnf -y install podman podman-compose<br>
sudo systemctl enable --now podman.socket<br>
flatpak install flathub io.podman_desktop.PodmanDesktop<br>
<br>
podman compose -f ./podman-compose.yml up -d<br>
<br>
UnZip data and copy to ./neo4j_home/import<br>
<br>
You must recreate container after copy files to neo4j_home/import <br>
(docker specific snapshot file system when create container)<br>
<br>
create db in neo4j Enterprise from Neo4j Desktop<br>
:use system;<br>
CREATE DATABASE hrm;<br>
:use hrm;<br>
<br>
Run Cypher query in Neo4j Desktop from dbscripts directory.<br>
01-customer_indexes.cql<br>
...<br>
07-get-one-customer-summer-2019-purchases.cql<br>
<br>
<img src="img/Neo4jDbScreenShort.jpg" width="600" />
<br>
mvn clean install<br>
or<br>
./mvnw clean install<br>
<br>
Run from IDE or command<br>
./mvnw spring-boot:run<br>

