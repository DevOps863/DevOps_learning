FROM maven AS build

WORKDIR /opt/shipping
COPY pom.xml .
RUN mvn dependency:resolve
COPY src /opt/shipping/src/
RUN mvn package

FROM openjdk:8-jre-alpine3.9
EXPOSE 8080
WORKDIR /opt/shipping
ENV CART_ENDPOINT=cart:8080
ENV DB_HOST=mysql
COPY --from=build /opt/shipping/target/shipping-1.0.jar shipping.jar

CMD [ "java", "-Xmn256m", "-Xmx768m", "-jar", "shipping.jar" ]
