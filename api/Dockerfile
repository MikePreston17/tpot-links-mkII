# GUIDE: https://itnext.io/smaller-docker-images-for-asp-net-core-apps-bee4a8fd1277

FROM alpine:3.9.4

# Add some libs required by .NET runtime 
RUN apk add --no-cache libstdc++ libintl

# https://github.com/dotnet/core/blob/master/Documentation/build-and-install-rhel6-prerequisites.md#troubleshooting
# RUN apk add --no-cache \ 
#     openssh libunwind \
#     nghttp2-libs libidn krb5-libs libuuid lttng-ust zlib \
#     libstdc++ libintl \
#     icu

EXPOSE 80
EXPOSE 443

# Copy 
WORKDIR /app
# COPY ./publish ./
COPY . .

ENTRYPOINT ["./publish/tpot_links_api.dll", "--urls", "http://0.0.0.0:80"]
# ENTRYPOINT ["./tpot_links_api", "--urls", "http://0.0.0.0:80"]