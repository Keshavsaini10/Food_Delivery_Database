# Static site served by nginx. Works on Render (Docker runtime) and any container host.
FROM nginx:1.27-alpine

# Render injects PORT at runtime; nginx's entrypoint renders templates with envsubst.
ENV PORT=10000

COPY nginx.conf.template /etc/nginx/templates/default.conf.template
COPY index.html /usr/share/nginx/html/index.html
COPY README.md /usr/share/nginx/html/README.md
COPY docs/ /usr/share/nginx/html/docs/
COPY proto/ /usr/share/nginx/html/proto/

EXPOSE 10000
