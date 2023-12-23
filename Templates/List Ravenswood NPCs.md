<%*
const dv = this.DataviewAPI
const escapePipe = s => new String(s).replace(/\|/, '\\|')
%>

<%
dv.pages("!#template")
	.where(f => f.file.path.includes("NPCs/Ravenswood"))
	.map(p => {
		let file = escapePipe(dv.fileLink(p.file.path));
		return `- ${file}`
	})
	.join("\n")
%>

