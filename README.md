# MicroserviceA

The Tip of the Day Microservice provides a daily motivational tip to be displayed in the Shift Scheduler program. It uses ZeroMQ for communication and responds with a random tip when requested.

To request a tip, the program must send a request message to the microservice. To request a Tip of the Day, send a request message to the microservice:
socket.send_string("get")
The microservice will respond containing the requested tip. To handle the response from the microservice:
response = socket.recv_string()
tip_data = json.loads(response)
print("Received Tip:", tip_data["tip"])

The message must contain the keyword "get" to receive a motivational tip. To receive data once the request is sent, the microservice responds in JSON format with a motivational tip. {"tip": "Stay positive and work hard!"}

![Screenshot 2025-02-23 142846](https://github.com/user-attachments/assets/df19a17f-065c-46bc-923a-81de2d3854d8)
