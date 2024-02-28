FROM python:3.11-rc-slim
WORKDIR /app
COPY . .
#RUN apt-get update
#RUN apt-get install --no-install-recommends curl -y
RUN pip install -r requirements.txt
EXPOSE 5000
CMD ["python", "app.py"]
