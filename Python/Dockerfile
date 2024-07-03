FROM python
COPY . .
RUN pip3 install -r requirements.txt
ENTRYPOINT ["python3"]
ENV FLASK_DEBUG=1
EXPOSE 8000
CMD ["web.py"]