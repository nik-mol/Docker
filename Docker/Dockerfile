FROM openjdk

COPY . /java

WORKDIR /java

EXPOSE 8001

# выполняется при создании образа
RUN javac Main.java

# выполняется каждый раз при запуске проекта (java Main)
CMD ["java", "Main"]