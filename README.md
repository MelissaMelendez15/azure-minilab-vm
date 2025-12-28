# azure-minilab-vm
## Descripción general
Este proyecto provisiona una infraestructura mínima en Microsoft Azure,
pensada para entornos de laboratorio DevOps y aprendizaje.

El objetivo es disponer de una base reproducible, sencilla y de bajo coste,
que pueda ampliarse posteriormente con herramientas de configuración,
monitorización y pipelines CI/CD.

## Arquitectura
La infraestructura se compone de una única máquina virtual Linux desplegada
dentro de una red virtual dedicada y protegida mediante un Network Security Group (NSG).

El diagrama de arquitectura se encuentra en el directorio `/diagrams`.

## Recursos creados
- Resource Group
- Virtual Network y Subnet
- Network Security Group con reglas de entrada restringidas
- Public IP
- Network Interface
- Máquina Virtual Linux (Ubuntu)

## Consideraciones de seguridad
- El acceso SSH está restringido a una única IP de confianza
- No se incluyen credenciales hardcodeadas
- Toda la infraestructura se gestiona mediante Terraform
- Uso consistente de tags para control de propiedad y costes

## Control de costes
Este laboratorio está diseñado para mantener un coste muy bajo:
- Tamaño reducido de la máquina virtual
- Uso mínimo de disco
- Apagado manual de la VM cuando no esté en uso
- Posibilidad de destruir y recrear los recursos en cualquier momento

## Estructura del proyecto
azure-minilab-vm/
├─ terraform/
│ ├─ main.tf
│ ├─ variables.tf
│ ├─ outputs.tf
│ ├─ providers.tf
│ └─ versions.tf
├─ ansible/ # opcional (fase futura)
├─ diagrams/
│ └─ architecture.mmd
└─ README.md

## Uso del proyecto
El código Terraform se añadirá en el siguiente paso del proyecto.

Flujo de trabajo previsto:
```bash
terraform init
terraform plan
terraform apply
terraform destroy
