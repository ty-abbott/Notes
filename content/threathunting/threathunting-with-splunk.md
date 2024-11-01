## Threat Hunting with splunk
This is going to be the notes that I create for the Immersive Labs campaign "APT29: Threat Hunting with Elasticsearch"

### lab1 Initial compromise 
It's common for adversaries to rely on users to execute malicious code unintentionally, and they often use social engineering tactics to achieve this. They might also use several file types that require user interaction to execute.

Threat hunters can detect this technique by monitoring command-line arguments for applications an attacker might use to get initial access, such as compression applications and instances of unknown applications spawning interactive shells.
