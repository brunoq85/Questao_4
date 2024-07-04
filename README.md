# Questão 4

Uma empresa registra os atendimentos por assunto e por ano em uma tabela.

Você precisa <strong>escrever um comando select</strong> que retorne o <strong>assunto</strong>, o <strong>ano</strong> e a <strong>quantidade</strong> de ocorrências, filtrando apenas assuntos que tenham <strong>mais de 3</strong> ocorrências <strong>no mesmo ano</strong>.

O comando deve ordenar os registros por <strong>ANO</strong> e por <strong>QUANTIDADE</strong> de ocorrências de forma <strong>DECRESCENTE</strong>.

<strong>Dados existentes na tabela:</strong>
<table>
  <thead>
    <tr>
      <td>ID</td>
      <td>ASSUNTO</td>
      <td>ANO</td>
    </tr>
  </thead>
  <tbody>
    <tr>   <td>4E8F4451-50E9-411F-BF44-134E28BEF561</td>  <td>Reclamacao atendimento</td>  <td>2021</td>
    <tr>   <td>F6DAB3D0-CF99-4323-B5AF-D787E451A33C</td>  <td>Reclamacao produto</td>      <td>2021</td>
    <tr>   <td>AF648480-5E31-48A4-B80C-19CC6D7F11A8</td>  <td>Reclamacao produto</td>      <td>2021</td>
    <tr>   <td>19C0084E-50B2-4EA4-89F0-65C458E9F8B6</td>  <td>Reclamacao cadastro</td>     <td>2021</td>
    <tr>   <td>7E922634-B905-4AD4-BBE0-F699CD7FD94E</td>  <td>Reclamacao atendimento</td>  <td>2021</td>
    <tr>   <td>6FAA1247-642C-4954-81CB-4409F9D84C0D</td>  <td>Reclamacao produto</td>      <td>2021</td>
    <tr>   <td>37A0793C-C4E8-4175-90EE-15052A187175</td>  <td>Reclamacao produto</td>      <td>2021</td>
    <tr>   <td>A44B5CF0-1CD4-46A3-A3FF-AB0C7CEE97BF</td>  <td>Reclamacao produto</td>      <td>2021</td>
    <tr>   <td>CC8730D6-B686-4938-BF5F-71358CAA3DF0</td>  <td>Reclamacao produto</td>      <td>2021</td>
    <tr>   <td>0B47828A-033E-46C4-8C7A-3218D3F59706</td>  <td>Reclamacao atendimento</td>  <td>2021</td>
    <tr>   <td>D5567A11-E71F-42E4-BDA5-84313B12965C</td>  <td>Reclamacao atendimento</td>  <td>2021</td>
    <tr>   <td>7DCDE5B4-208A-45D8-9F10-DD4DFD3829C8</td>  <td>Reclamacao produto</td>      <td>2022</td>
    <tr>   <td>D3CD0816-2072-4045-B30D-0EE34DE86141</td>  <td>Reclamacao produto</td>      <td>2022</td>
    <tr>   <td>8B4AA748-64F1-4A1F-A7D9-5CBBDDD3975E</td>  <td>Reclamacao atendimento</td>  <td>2022</td>
    <tr>   <td>7E5B0F44-7770-47CB-99EE-9513930D285B</td>  <td>Reclamacao atendimento</td>  <td>2022</td>
    <tr>   <td>15FA67FC-C40F-4EA6-8F94-C9AEA19FF277</td>  <td>Reclamacao atendimento</td>  <td>2022</td>
    <tr>   <td>7004F15B-7637-45C7-98C2-E2DFDC29EB15</td>  <td>Reclamacao cadastro</td>     <td>2022</td>
    <tr>   <td>35C695C2-2ADC-46D8-B356-18C42D959E69</td>  <td>Reclamacao cadastro</td>     <td>2022</td>
    <tr>   <td>092E86EE-CA24-466C-860A-91210A60E094</td>  <td>Reclamacao cadastro</td>     <td>2022</td>
    <tr>   <td>180C3126-CB7B-48D0-91AC-27038091D764</td>  <td>Reclamacao cadastro</td>     <td>2022</td>
    <tr>   <td>2BFB7412-D85C-4A89-A745-D61B93CF9E8E</td>  <td>Reclamacao cadastro</td>     <td>2022</td>
    <tr>   <td>97290DA8-B9C2-49B7-AD0E-0BF754A8C4DB</td>  <td>Reclamacao cadastro</td>     <td>2022</td>
    <tr>   <td>10C3D139-0812-4432-8D2D-5330813BF83D</td>  <td>Reclamacao cadastro</td>     <td>2022</td>
    <tr>   <td>332EF92F-00F5-44C1-835E-F88481BBB0A8</td>  <td>Reclamacao cadastro</td>     <td>2022</td>    
  </tbody>
</table>


Resultado esperado:

Comandos para criação da tabela e inserção dos registros:

```
-- ORACLE
CREATE TABLE atendimentos (
 id  RAW(16) DEFAULT SYS_GUID() NOT NULL,
 assunto VARCHAR2(100) NOT NULL,
 ano NUMBER(4)
);

INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao atendimento','2021');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao produto','2021');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao produto','2021');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao cadastro','2021');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao atendimento','2021');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao produto','2021');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao produto','2021');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao produto','2021');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao produto','2021');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao atendimento','2021');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao atendimento','2021');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao produto','2022');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao produto','2022');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao atendimento','2022');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao atendimento','2022');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao atendimento','2022');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao cadastro','2022');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao cadastro','2022');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao cadastro','2022');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao cadastro','2022');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao cadastro','2022');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao cadastro','2022');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao cadastro','2022');
INSERT INTO atendimentos (assunto, ano) VALUES ('Reclamacao cadastro','2022');
COMMIT;
```

Resposta:
```
SELECT assunto, ano, COUNT(*) as quantidade
FROM atendimentos
GROUP BY assunto, ano
HAVING COUNT(assunto) > 3
ORDER BY ano DESC, quantidade DESC
```
