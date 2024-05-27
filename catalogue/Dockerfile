FROM python:latest as builder
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .


FROM python:latest-alpine
WORKDIR /final_build
COPY --from=builder /usr/local/lib/python3.9/site-packages /usr/local/lib/python3.9/site-packages
COPY --from=builder /usr/local/bin/gunicorn /usr/local/bin/gunicorn
COPY --from=builder /app .
EXPOSE 5000
CMD ["gunicorn","app:app","--bind","0.0.0.0:5000"]



