import random
import time
class Sensor:
    def _init_(self, name):
        self.name = name

    def read_data(self):
        if self.name == "temperature":
            return round(random.uniform(15.0, 35.0), 2)  
        elif self.name == "humidity":
            return round(random.uniform(30.0, 90.0), 2) 
        elif self.name == "soil_moisture":
            return round(random.uniform(0.0, 100.0), 2) 
            
            class SmartAgricultureMonitor:
                def _init_(self):
                    self.sensors = {
                        "temperature": 
                        Sensor("temperature"),
                        "humidity":
                        Sensor("humidity"),
                        "soil_moisture":
                        Sensor("soil_moisture"),
                    }
                    
                def gather_data(self):
                    data = {}
                    for sensor_name, sensor in self.sensors.items():
                        data[sensor_name] = sensor.read_data()
                        return data
                        
                def analyze_data(self, data):
                    if data["temperature"] > 30:
                        print("Warning: High temperature detected!")
                    if data["humidity"] < 40:
                        print("Warning: Low humidity detected!")
                    if data["soil_moisture"] < 20:
                        print("Warning: Soil moisture is low!")

                def run(self):
                    while True:
                        data = self.gather_data()
                        print(f"Sensor Data: {data}")
                        self.analyze_data(data)
                        time.sleep(5) 
                    if _name_ == "_main_":
                        monitor = SmartAgricultureMonitor()
                        monitor.run()
