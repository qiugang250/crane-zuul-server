FROM java:8 as builder
WORKDIR /app
ADD *.java /app
RUN javac *.java

FROM java:8-jre-alpine
WORKDIR /app
COPY --from=builder /app/*.class /app
ENTRYPOINT java -jar  -Duser.timezone=GMT+8 /app/*jar --spring.profiles.active=$PROFILE --config.uri=$CONFIGURL