
--- 
Erstellt: 2025-09-12    13:15 
Tags: #Programming/JavaScript/React 
Link Up: [[React]]
Link Down:

--- 
### Wie man eine React App aufsetzt 
Es gibt 2 Methoden um eine React App zu erstellen. 
- **Create-React-App:** Komplettes Starter Kit für React Applikation
	- Alles ist bereits Konfiguriert (ESLint, Prettier, Jest, etc.)
	- Es ist dennoch sehr alt und sollte nicht in größeren Projekten verwendet werden, sondern nur für Test oder Übungszwecke 
- **Vite:** Modernes Build Tool, welches ein Template nutzt um React Apps zu erstellen
	- Problem an dieser Sache ist, dass man Tools wie ESLint etc. manuell installieren muss
	- Vorteil ist, dass extrem schnell ist (Hot Module Replacement(HMR)) 

##### Steps
- `npm i create vite@latest`

Die schritte dort befolgen und somit ist React mit Vite installiert, wenn man das Frontend getrennt vom backend hat, dann sollte man den Port in der `vit.config.ts` noch ändern, hierzu einfach:
```js
export default defineConfig({
	plugins: [react()],
	server: {
		opern: true,
		port: 3000  //Dies ist der Port vom backend
	}
})
```


# Aufsetzung mit Create-React-App
![[Pasted image 20250912133021.png]]
Mit diesen Befehl erstellen wir in den aktuellen Ordner eine neue React App mit dem Namen "pizza-menu"




## References
1. 
